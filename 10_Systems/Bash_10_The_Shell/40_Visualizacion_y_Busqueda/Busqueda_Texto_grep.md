# Busqueda de Texto: grep

`grep` (Global Regular Expression Print) busca cadenas de texto **DENTRO** de los archivos. Es el Google de tu terminal.

**Sintaxis:** `grep "texto_a_buscar" [archivo]`

## 1. Busqueda Basica

```
# Buscar la palabra "error" en el log
grep "error" app.log

# Buscar ignorando mayusculas/minusculas (-i)
grep -i "error" app.log
```

## 2. Busqueda Recursiva (-r)

Busca en una carpeta y todas sus subcarpetas. Vital para programadores buscando donde se define una variable.

# Buscar "db_password" en toda la carpeta /etc
grep -r "db_password" /etc/

## 3. Busqueda Inversa (-v)

Muestra todo LO QUE NO coincida. Util para filtrar ruido.

# Mostrar todo el archivo EXCEPTO las lineas de debug
grep -v "DEBUG" production.log

## 4. Grep con Pipes (Tuberias)

`grep` brilla cuando filtras el output de otros comandos.

# Filtrar procesos: ¿Esta corriendo nginx?
ps aux | grep nginx

# Filtrar historia: ¿Como era el comando de ssh que use ayer?
history | grep ssh

# Contar cuantas veces aparece una palabra (-c)
cat accesos.log | grep -c "404 Not Found"

**Resumen de Banderas Clave:**

- `-i`: Ignore case.
    
- `-r`: Recursive.
    
- `-v`: Invert match.
    
- `-n`: Muestra el numero de linea donde encontro el texto.
    
- `-l`: Muestra solo el nombre del archivo, no el texto.