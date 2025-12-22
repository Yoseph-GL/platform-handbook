# The Ultimate Bash Boilerplate

No empieces tus scripts en blanco. Usa esta plantilla. Incluye:
1.  **Strict Mode:** Para fallar seguro.
2.  **Magic Path:** Para encontrar sus propios archivos.
3.  **Help Function:** Documentación automática.
4.  **Logging:** Colores y timestamps.
5.  **Cleanup:** Limpieza automática al salir.

### La Plantilla (`template.sh`)

```bash
#!/usr/bin/env bash

# 1. STRICT MODE (Seguridad primero)
set -euo pipefail
IFS=$'\n\t'

# 2. MAGIC PATH (Donde estoy parado)
# Permite llamar al script desde cualquier lugar y que sepa encontrar sus librerias
SCRIPT_DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
readonly SCRIPT_DIR

# 3. CONSTANTES Y DEFAULTS
readonly SCRIPT_NAME=$(basename "$0")
LOG_FILE="/tmp/${SCRIPT_NAME%.*}.log"
VERBOSE=0

# Colores para output (Solo si es terminal interactiva)
if [[ -t 1 ]]; then
    RED='\033[0;31m'
    GREEN='\033[0;32m'
    YELLOW='\033[0;33m'
    NC='\033[0m' # No Color
else
    RED='' GREEN='' YELLOW='' NC=''
fi

# 4. TRAP Y CLEANUP
cleanup() {
    # Codigo que corre SIEMPRE al final (exito o error)
    # Borrar temporales, cerrar conexiones, etc.
    local exit_code=$?
    if (( exit_code != 0 )); then
        echo -e "${RED}[ERROR] El script termino con codigo $exit_code${NC}"
    fi
    # rm -f /tmp/tempfile...
}
trap cleanup EXIT

# 5. FUNCIONES DE LOGGING
log_info() { echo -e "${GREEN}[INFO]${NC} $1" | tee -a "$LOG_FILE"; }
log_warn() { echo -e "${YELLOW}[WARN]${NC} $1" | tee -a "$LOG_FILE"; }
log_err()  { echo -e "${RED}[ERR]${NC}  $1" | tee -a "$LOG_FILE" >&2; }

usage() {
    cat <<EOF
Uso: $SCRIPT_NAME [opciones] <archivo_destino>

Descripcion:
  Esta es una plantilla profesional para scripts de Bash.

Opciones:
  -h, --help      Muestra esta ayuda.
  -v, --verbose   Activa modo detallado.
  
Ejemplo:
  $SCRIPT_NAME -v /var/www/html
EOF
    exit 1
}

# 6. PARSEO DE ARGUMENTOS
parse_params() {
    # Validar que haya argumentos
    if [[ $# -eq 0 ]]; then usage; fi

    while :; do
        case "${1-}" in
        -h | --help) usage ;;
        -v | --verbose) 
            VERBOSE=1 
            set -x # Debug mode nativo de bash
            ;;
        -?*) log_err "Opcion desconocida: $1"; usage ;;
        *) break ;; # Detener loop si no es bandera (es argumento posicional)
        esac
        shift
    done

    # Argumentos restantes
    ARGS=("$@")
    
    # Validacion de argumentos requeridos
    if [[ ${#ARGS[@]} -eq 0 ]]; then
        log_err "Falta argumento obligatorio: archivo_destino"
        usage
    fi
}

# 7. LOGICA PRINCIPAL (MAIN)
main() {
    parse_params "$@"
    
    local destino="${ARGS[0]}"
    
    log_info "Iniciando script..."
    log_info "Modo Verbose: $VERBOSE"
    log_info "Destino: $destino"
    
    # Simulacion de trabajo
    sleep 1
    
    if [[ -d "$destino" ]]; then
        log_info "El directorio existe. Procesando..."
    else
        log_warn "El directorio no existe. Creando..."
        # mkdir -p "$destino"
    fi
    
    log_info "Finalizado correctamente."
}

# Iniciar
main "$@"
```
