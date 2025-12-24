# Expansion de Parametros (Parameter Expansion)

Bash puede manipular strings DENTRO de la variable, sin llamar a comandos lentos como `sed` o `awk`. Esto es ultra rapido.

Sintaxis general: `${variable...}`

## 1. Valores por Defecto
Manejo de nulos. Vital para scripts robustos.

| Sintaxis | Descripcion |
|:---|:---|
| `${VAR:-default}` | Si VAR esta vacia/nula, usa "default". (No asigna). |
| `${VAR:=default}` | Si VAR esta vacia/nula, **ASIGNA** "default" a VAR. |
| `${VAR:?error}` | Si VAR esta vacia, **DETIENE** el script y muestra "error". |

**Ejemplo:**
```
nombre=${1:-"Visitante"}
echo "Hola, $nombre"
# Si ejecutas ./script.sh -> Hola, Visitante
# Si ejecutas ./script.sh Carlos -> Hola, Carlos
```

## 2. Manipulacion de Strings

### Longitud

texto="Hola Mundo"
echo ${#texto}  # Salida: 10

### Substring (Cortar)

Format: `${var:offset:length}`
fecha="2023-10-25" anio=${fecha:0:4} # 2023
mes=${fecha:5:2} # 10

### Eliminar Patrones (Trimming)

- `%` = Cortar desde el final (Cola).
    
- `#` = Cortar desde el inicio (Cabeza).

archivo="imagen.tar.gz"

# Quitar extension (desde el final)
echo ${archivo%.*}      # imagen.tar
echo ${archivo%%.*}     # imagen (Doble % es codicioso/greedy)

# Quitar ruta (desde el inicio)
ruta="/var/log/syslog"
echo ${ruta#*/}         # var/log/syslog
echo ${ruta##*/}        # syslog (Solo el nombre del archivo)