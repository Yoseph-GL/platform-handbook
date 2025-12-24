# Librerias y Modularidad: source

No escribas scripts de 1000 lineas. Divide y venceras. Crea archivos separados para funciones comunes (Logging, Colores, DB) e importalos.

## 1. El comando `source`
Carga el contenido de otro archivo en el contexto actual.

* Sintaxis larga: `source utils.sh`
* Sintaxis corta: `. utils.sh` (Punto espacio archivo).

## 2. Patron de Importacion Robusto (Magic Path)
Si tu script importa `source utils.sh` y ejecutas el script desde otra carpeta, fallara porque no encontrara el archivo.

**Solucion Profesional:**
Usa siempre rutas absolutas dinamicas basandote en la ubicacion del script.

```
#!/bin/bash

# Obtener la carpeta donde vive ESTE script
SCRIPT_DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"

# Importar libreria relativa a esa carpeta
source "${SCRIPT_DIR}/libs/utils.sh"
source "${SCRIPT_DIR}/conf/colores.sh"

log_info "Librerias cargadas correctamente"
```

## 3. Ejemplo de Libreria (`libs/utils.sh`)
# Esto no se ejecuta, solo define funciones
log_info() {
    echo "[INFO] $1"
}

log_error() {
    echo "[ERROR] $1" >&2
}