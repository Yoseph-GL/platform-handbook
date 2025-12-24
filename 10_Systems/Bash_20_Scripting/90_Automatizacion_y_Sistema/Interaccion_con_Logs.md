# Logging: Interacción con Logs

Un script profesional no imprime en pantalla (nadie está mirando la pantalla a las 3 AM). Un script profesional escribe en logs.

## 1. Logging Manual (Redireccion)
La forma más simple. Añades fecha y mensaje a un archivo de texto.

```
LOG_FILE="/var/log/mi_app/backup.log"

log() {
    local mensaje=$1
    local fecha=$(date "+%Y-%m-%d %H:%M:%S")
    echo "[$fecha] [INFO] $mensaje" >> "$LOG_FILE"
}

# Uso
log "Iniciando proceso..."
```

## 2. El comando `logger` (System Log)

Linux tiene un sistema centralizado de logs (`syslog` o `journald`). Usar `logger` envía tus mensajes ahí, donde herramientas profesionales pueden leerlos.
# Enviar mensaje al sistema
logger "MiScript: El backup finalizó correctamente"

# Con prioridad (user.info, local0.err, etc)
logger -p local0.err "MiScript: Error critico en base de datos"

**Ventaja:** Tus logs aparecen en `/var/log/syslog` automáticamente y se rotan solos.

## 3. Log Rotation (Teoría)

Si tu script escribe 1GB de logs al día, llenarás el disco en un mes. Linux usa **logrotate** para:

1. Comprimir logs viejos (`backup.log.1.gz`).
    
2. Borrar los muy antiguos (más de 30 días).
    