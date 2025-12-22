# Cheat Sheet: Bash Scripting Best Practices

## 1. El Encabezado Seguro (Boilerplate)
Empieza SIEMPRE tus scripts con esto para evitar errores silenciosos.

#!/bin/bash
set -euo pipefail
IFS=$'\n\t'

- `set -e`: Aborta si un comando falla (exit code != 0).
    
- `set -u`: Aborta si usas una variable no definida.
    
- `set -o pipefail`: Detecta errores incluso dentro de un pipe (`cmd1 | cmd2`). 

## 2. Variables y Naming

- **MAYUSCULAS:** Solo para constantes exportadas o variables de entorno (`API_KEY`).
    
- **snake_case:** Para variables locales (`nombre_archivo`).
    
- **Siempre entre comillas:** Protege espacios en blanco.
    
    - MAL: `cp $origen $destino`
        
    - BIEN: `cp "${origen}" "${destino}"`

## 3. Condicionales Modernos

Usa siempre `[[ ]]` en lugar de `[ ]`. Es mas seguro y potente.

# Comparar Strings
if [[ "${usuario}" == "root" ]]; then
    echo "Peligro"
fi

# Comparar Numeros
if (( contador > 10 )); then
    echo "Limite excedido"
fi

# Chequear Archivos
if [[ -f "config.yaml" ]]; then
    echo "Archivo existe"
fi

## 4. Arrays (Listas)

No uses strings separados por espacios para listas, usa arrays reales.

servidores=("web01" "web02" "db01")

for srv in "${servidores[@]}"; do
    echo "Conectando a $srv..."
done
## 5. Funciones

Define funciones para logica repetida. Usa `local` para variables

log_info() {
    local mensaje=$1
    echo "[INFO] $(date +%F) - ${mensaje}"
}

log_info "Iniciando backup..."

## 6. Debugging Rapido

Si el script falla, ejecutalo asi para ver paso a paso que hace:

bash -x mi_script.sh

| **Codigo**           | **Chequeo**                              |
| -------------------- | ---------------------------------------- |
| `[[ -z "$VAR" ]]`    | ¿La variable esta vacia?                 |
| `[[ -n "$VAR" ]]`    | ¿La variable tiene contenido?            |
| `[[ -f "$FILE" ]]`   | ¿Es un archivo?                          |
| `[[ -d "$DIR" ]]`    | ¿Es un directorio?                       |
| `[[ -x "$SCRIPT" ]]` | ¿Es ejecutable?                          |
| `$?`                 | Exit code del comando anterior (0=Exito) |