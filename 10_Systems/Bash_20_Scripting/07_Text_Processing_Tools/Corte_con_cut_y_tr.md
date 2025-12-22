# Herramientas Ligeras: cut y tr

Antes de usar herramientas complejas, usa estas para tareas simples de limpieza y extraccion.

## 1. cut (Cortar columnas)
Ideal para archivos delimitados (CSV, /etc/passwd).

**Sintaxis:** `cut -d "delimitador" -f "numero_campo"`

```
# Ejemplo: Extraer usuarios del sistema
# Formato /etc/passwd: root:x:0:0:...
cut -d ":" -f 1 /etc/passwd
```

- `-d`: Define el separador (por defecto es TAB).
    
- `-f`: Field (Campo). Puede ser `1`, `1,3` o `1-5`.
    
- `-c`: Cortar por caracter (ej: caracteres 1 al 10).
    

## 2. tr (Translate / Trim)

Funciona SOLO con STDIN (tuberias). Sirve para reemplazar o borrar caracteres individuales.
# Convertir a mayusculas
echo "hola" | tr 'a-z' 'A-Z'

# Borrar caracteres especificos (-d)
# Ejemplo: Quitar comillas de un JSON
echo '"valor"' | tr -d '"'

# Comprimir espacios repetidos (-s)
# Convierte "a    b  c" en "a b c"
echo "a    b" | tr -s ' '