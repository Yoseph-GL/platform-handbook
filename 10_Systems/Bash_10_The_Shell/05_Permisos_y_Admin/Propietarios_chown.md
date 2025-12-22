# Propietarios y Grupos: chown

Los permisos (rwx) no sirven de nada si no controlas QUIEN es el dueño del archivo.

## 1. Concepto Usuario:Grupo
Cada archivo pertenece a:
1.  **Un Usuario Owner:** Quien lo creo (generalmente).
2.  **Un Grupo Owner:** Un equipo de usuarios que comparten permisos.

Ejemplo en `ls -l`:
`drwxr-xr-x  juan  developers  4096 ...`
* Dueño: `juan`
* Grupo: `developers`

## 2. El comando chown (Change Owner)

Cambia el dueño y/o el grupo. Requiere `sudo`.

**Sintaxis:** `sudo chown [usuario]:[grupo] [archivo]`

```
# Cambiar solo el dueño
sudo chown admin config.xml

# Cambiar dueño y grupo a la vez
sudo chown www-data:www-data index.html

# Cambiar recursivamente (CARPETA COMPLETA)
# Vital para deployments web
sudo chown -R www-data:www-data /var/www/html/
```

## 3. El comando chgrp

Cambia solo el grupo (menos usado, ya que `chown` hace ambas cosas).

sudo chgrp docker users.txt
