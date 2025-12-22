# Script de Monitoreo de Recursos

Este script verifica el estado de Disco, RAM y CPU. Si algún valor supera el límite, envía una alerta al log del sistema (syslog). Ideal para correr con **Cron**.

### El Código (`monitor.sh`)

Copia esto en un archivo `.sh`, dale `chmod +x` y pruébalo.

```bash
#!/bin/bash
set -euo pipefail

# --- CONFIGURACION ---
DISK_THRESHOLD=90     # Alerta si disco > 90% ocupado
RAM_THRESHOLD=500     # Alerta si memoria libre < 500 MB
SERVER_NAME=$(hostname)

# --- FUNCIONES ---

check_disk() {
    # df -h / | tail -1 | awk '{print $5}' | tr -d '%'
    # 1. df -h / : Muestra espacio de raiz
    # 2. awk : Obtiene la columna 5 (Porcentaje)
    # 3. tr : Quita el simbolo %
    
    local usage
    usage=$(df -h / | awk 'NR==2 {print $5}' | tr -d '%')
    
    if (( usage > DISK_THRESHOLD )); then
        logger -p local0.alert "ALERTA [$SERVER_NAME]: Disco critico al $usage%"
        echo "ALERTA: Disco al $usage%"
    else
        echo "Disco OK: $usage%"
    fi
}

check_ram() {
    # free -m : Memoria en Megas
    # awk : Busca la fila "Mem:" y toma columna 7 (Available/Disponible)
    
    local free_mem
    free_mem=$(free -m | awk '/^Mem/ {print $7}')
    
    if (( free_mem < RAM_THRESHOLD )); then
        logger -p local0.alert "ALERTA [$SERVER_NAME]: Poca RAM libre ($free_mem MB)"
        echo "ALERTA: Poca RAM ($free_mem MB)"
    else
        echo "RAM OK: $free_mem MB libres"
    fi
}

check_cpu_load() {
    # uptime muestra: load average: 0.05, 0.10, 0.15
    # Tomamos el primer valor (ultimo minuto)
    local load
    load=$(uptime | awk -F'load average:' '{ print $2 }' | cut -d, -f1 | tr -d ' ')
    
    # Nota: Comparar decimales en bash puro es dificil, usamos awk para el if
    if awk "BEGIN {exit !($load > 2.0)}"; then
        logger -p local0.warning "ALERTA [$SERVER_NAME]: CPU Load alta ($load)"
        echo "ALERTA: CPU Load alta ($load)"
    else
        echo "CPU OK: Load $load"
    fi
}

# --- MAIN ---
echo "--- Iniciando Monitoreo $(date) ---"
check_disk
check_ram
check_cpu_load
```
