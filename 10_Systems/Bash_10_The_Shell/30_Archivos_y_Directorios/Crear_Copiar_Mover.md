# Manipulacion Basica: Crear, Copiar, Mover

En Linux, todo es un archivo. Aqui estan las herramientas para gestionarlos.

## 1. Creacion

| Comando      | Descripcion                                                | Ejemplo                                                   |
| :----------- | :--------------------------------------------------------- | :-------------------------------------------------------- |
| **mkdir**    | Crea directorios (carpetas).                               | `mkdir logs`                                              |
| **mkdir -p** | **Parents:** Crea toda la ruta si no existe.               | `mkdir -p proyecto/src/assets` (Crea 3 carpetas de golpe) |
| **touch**    | Crea un archivo vacio (o actualiza su fecha si ya existe). | `touch index.html`                                        |

## 2. Copiado (cp)

El comando `cp` duplica contenido.
Sintaxis: `cp [origen] [destino]`

* **Archivo simple:**
  ```
  cp config.xml config_backup.xml
``


**Directorios (Recursivo):** Para copiar una carpeta y todo su contenido, NECESITAS la bandera `-r`.

cp -r /var/www/html /home/backup/sitio_web

## 3. Mover y Renombrar (mv)

En Linux, "mover" y "cambiar nombre" son la misma operacion a nivel de sistema de archivos.

- **Mover de lugar:**
   mv archivo.txt /tmp/

- **Renombrar (Moverse "ahi mismo"):**
   mv viejo_nombre.txt nuevo_nombre.txt
   
**Tip:** Al mover archivos criticos, usa `mv -n` (no-clobber) para evitar sobrescribir un archivo existente en el destino por accidente.