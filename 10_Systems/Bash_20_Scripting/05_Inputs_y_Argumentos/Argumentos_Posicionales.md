# Argumentos Posicionales (CLI Arguments)

Son los valores que escribes **después** del nombre del script al ejecutarlo.
`./deploy.sh prod v2.0` -> `prod` es el 1, `v2.0` es el 2.

## 1. Variables Automaticas

| Variable | Descripcion |
|:---|:---|
| `$0` | El nombre del script (`./deploy.sh`). |
| `$1` - `$9` | Los argumentos en orden. |
| `${10}` | Argumento 10 o superior (requiere llaves). |
| `$#` | **Conteo:** Cantidad total de argumentos pasados. |
| `$@` | **Todos:** La lista completa de argumentos (iterable). |

## 2. Validacion de Argumentos
Antes de hacer nada, verifica que te hayan dado lo que necesitas.

```
if [[ $# -lt 2 ]]; then
    echo "Uso: $0 [entorno] [version]"
    exit 1
fi

entorno=$1
version=$2
```

## 3. El comando `shift`

Mueve los argumentos a la izquierda. El `$2` se vuelve `$1`, el `$3` se vuelve `$2`, y el `$1` original desaparece. Vital para loops que procesan argumentos uno por uno.
echo "Argumento 1 es: $1" # Imprime "A"
shift
echo "Argumento 1 es ahora: $1" # Imprime "B"