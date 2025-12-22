# Streams: STDIN, STDOUT, STDERR

En Linux, cada programa que ejecutas tiene siempre 3 canales de datos abiertos por defecto. Se llaman "File Descriptors" (FD).

## Los 3 Canales

| FD | Nombre | Descripcion | Origen/Destino Default |
|:---|:---|:---|:---|
| **0** | **STDIN** (Standard Input) | Datos que ENTRAN al programa. | Tu Teclado. |
| **1** | **STDOUT** (Standard Output) | Datos que SALEN (resultados exitosos). | Tu Pantalla. |
| **2** | **STDERR** (Standard Error) | Mensajes de ERROR. | Tu Pantalla. |

## ¿Por que estan separados?
Para que puedas guardar los datos buenos en un archivo (`datos.txt`) y tirar los errores a la basura (o a un log de errores aparte), sin mezclar la informacion.

> **Ejemplo Visual:**
> Si ejecutas `ls archivo_existe archivo_no_existe`:
> 1. `ls` encuentra uno -> Lo manda al canal **1**.
> 2. `ls` no encuentra el otro -> Manda el aviso al canal **2**.
> En tu pantalla se ven juntos, pero internamente viajan por cables distintos.