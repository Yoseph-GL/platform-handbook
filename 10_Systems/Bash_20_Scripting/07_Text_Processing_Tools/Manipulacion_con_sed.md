# Stream Editor: sed

`sed` edita texto flujo a flujo. Es famoso por "Buscar y Reemplazar".

## 1. Sustitucion Basica (s)
Sintaxis: `s/buscar/reemplazar/flags`

```
# Reemplazar la PRIMERA aparicion de "error" por "alerta"
echo "error fatal error" | sed 's/error/alerta/'
# Salida: alerta fatal error

# Reemplazar TODAS las apariciones (Global - g)
echo "error fatal error" | sed 's/error/alerta/g'
# Salida: alerta fatal alerta
```

## 2. Edicion de Archivos (-i)

Por defecto `sed` solo imprime el cambio en pantalla. Para guardar el cambio en el archivo, usa `-i` (in-place).
# Cambiar puerto 80 a 8080 en config
sed -i 's/80/8080/g' nginx.conf

**Advertencia:** `sed -i` es destructivo. Haz backup o usa `sed -i.bak` para crear respaldo automatico.

## 3. Borrar Lineas (d)
# Borrar la linea 5
sed '5d' archivo.txt

# Borrar lineas que contengan "comentario"
sed '/comentario/d' script.sh

# Borrar lineas VACIAS
sed '/^$/d' texto.txt