# Operadores de Redireccion

La redireccion cambia el destino de los streams. En lugar de imprimir en pantalla, mandas los datos a archivos.

## 1. Salida Estandar (STDOUT)

### `>` (Sobrescribir)
Guarda el output en un archivo. Si el archivo existia, **LO BORRA** y escribe encima.
```
echo "Hola Mundo" > saludo.txt
```

### `>>` (Adjuntar / Append)

Agrega el output al FINAL del archivo. No borra nada.
echo "Otra linea" >> saludo.txt

## 2. Error Estandar (STDERR)

Para redireccionar errores, debes especificar el descriptor `2`.
# Guardar errores en un log separado
ls /carpeta_rara 2> errores.log

## 3. Combinaciones Avanzadas

### Fusionar STDOUT y STDERR (`2>&1`)

A veces quieres todo (exitos y errores) en un solo archivo.
# "Manda el 2 a donde apunte el 1"
comando_largo > todo.log 2>&1

### El Agujero Negro (`/dev/null`)

Para silenciar un comando completamente.
# Ejecutar, no mostrar nada y no guardar nada
comando_ruidoso > /dev/null 2>&1

## 4. Entrada Estandar (`<`)

Menos comun. Alimenta un comando con un archivo en lugar del teclado.
# Inyectar base de datos
mysql -u root -p < backup_db.sql