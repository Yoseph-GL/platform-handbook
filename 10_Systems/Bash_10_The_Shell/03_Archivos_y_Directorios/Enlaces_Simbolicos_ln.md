# Enlaces (Links): ln

Los enlaces son punteros a archivos. Permiten que un archivo exista en multiples lugares sin duplicar el espacio en disco.

## 1. Soft Links (Enlaces Simbolicos)
Son como los "Accesos Directos" de Windows.
* Si borras el original, el enlace se rompe ("Dangling link").
* Pueden apuntar a directorios.
* Pueden cruzar sistemas de archivos (discos).

**Sintaxis:** `ln -s [archivo_real] [nombre_del_link]`

```
# Ejemplo Practico: Nginx / Apache
# El archivo real esta en sites-available, el link en sites-enabled
ln -s /etc/nginx/sites-available/miweb /etc/nginx/sites-enabled/miweb
**Nota:** Usa siempre **rutas absolutas** al crear soft links para evitar que se rompan si mueves el link de lugar.
```
## 2. Hard Links

Son duplicados del indice del archivo (inode).

- El archivo tiene dos nombres validos.
    
- Si borras el original, el Hard Link **sigue funcionando** y contiene los datos.
    
- No funcionan con directorios.
    
- Solo funcionan en la misma particion de disco.

ln archivo_original copia_dura # (Casi no se usa en operaciones diarias, enfocate en -s)
## Como identificarlos

Al hacer un `ls -l`:
lrwxrwxrwx 1 root root 4 ago 10 15:00 mylink -> /var/www/html
- La `l` al inicio indica que es un Link.
    
- La flecha `->` te dice a donde apunta realmente.