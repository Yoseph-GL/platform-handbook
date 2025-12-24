# Procesamiento de Columnas: awk

`awk` es un lenguaje de programacion completo diseñado para procesar texto en columnas. Si `cut` se queda corto, `awk` es la solucion.

## 1. Sintaxis Basica
`awk 'patron { accion }' archivo`

Las columnas se llaman `$1`, `$2`, `$3`... `$0` es la linea completa.

```
# Imprimir solo la primera columna (Ej: PIDs de ps)
ps aux | awk '{print $1}'
```

## 2. Separadores Personalizados (-F)

Por defecto usa espacios/tabs.
# Leer CSV separado por comas
echo "juan,25,admin" | awk -F ',' '{print $1 " es " $3}'
# Salida: juan es admin

## 3. Filtrado Inteligente (Condiciones)

`awk` puede usar `if` implicitos.
# Imprimir procesos que consumen mas del 50% de CPU (Columna 3 en ps aux)
ps aux | awk '$3 > 50.0 {print $0}'

# Sumar una columna (Totalizar bytes de ls -l)
ls -l | awk '{suma += $5} END {print suma}'

**Diferencia Clave:** En Bash `$1` es el primer argumento del script. En Awk `$1` es la primera columna del texto.