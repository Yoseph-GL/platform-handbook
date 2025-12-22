# Tuberias (Pipes) `|`

El operador `|` (pipe) conecta la **SALIDA (STDOUT)** del comando izquierdo con la **ENTRADA (STDIN)** del comando derecho.

`Comando A` -> `|` -> `Comando B`

## Filosofia Unix
"Haz una cosa y hazla bien. Trabaja junto a otros programas."

## Ejemplos Esenciales

### 1. Paginacion de salida larga
Si un comando escupe 1000 lineas, usas `less` para frenarlo.
```
cat archivo_gigante.log | less
```

### 2. Filtrado en tiempo real

La combinacion mas usada del mundo.
ps aux | grep "python"
# 1. ps saca la lista de procesos.
# 2. El pipe se la pasa a grep.
# 3. grep filtra y muestra solo lo que dice python.

### 3. Conteo de lineas

¿Cuantos archivos tengo en esta carpeta?
ls -1 | wc -l
# ls -1: Lista un archivo por linea.
# wc -l: Cuenta las lineas (Word Count).

### 4. Tuberias Multiples

Puedes encadenar infinitamente.
cat access.log | grep "404" | sort | uniq -c
# Lee log -> Filtra errores -> Ordena -> Cuenta repetidos