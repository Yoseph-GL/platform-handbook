# Parsing de Banderas: getopts

Si quieres hacer scripts profesionales como `ls -la` o `git commit -m "msg"`, NO uses `$1` y `$2`. Usa `getopts`.

## Estructura Estandar

`getopts` procesa las opciones una por una dentro de un `while`.

**Sintaxis de la cadena de opciones:** `"f:v"`
* `f:` (Con dos puntos) -> La opción `-f` requiere un valor (argumento).
* `v` (Sin dos puntos) -> La opción `-v` es un switch booleano (on/off).

```
#!/bin/bash

# Inicializar variables
archivo=""
verbose=0

# Loop magico
while getopts "f:v" flag; do
    case "${flag}" in
        f) archivo="${OPTARG}" ;;  # Guardar el argumento en variable
        v) verbose=1 ;;            # Activar modo verbose
        *) echo "Opcion invalida"; exit 1 ;;
    esac
done

# Validacion
if [[ -z "$archivo" ]]; then
    echo "Error: Debes especificar un archivo con -f"
    exit 1
fi

echo "Procesando $archivo (Verbose: $verbose)..."
```

**Nota Tecnica:** `getopts` solo soporta banderas cortas (`-f`). Para banderas largas (`--file`), necesitas usar `getopt` (sin la s) o parsing manual, lo cual es mas complejo.