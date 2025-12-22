# Borrado de Archivos: rm y rmdir

En la terminal **NO EXISTE LA PAPELERA DE RECICLAJE**. Lo que borras, desaparece para siempre.

## 1. Borrar Directorios Vacios
La forma segura de borrar carpetas que ya no usas.

```
rmdir carpeta_vacia/
# Falla si la carpeta tiene aunque sea un archivo adentro.
```
## 2. El comando rm (Remove)

Es la herramienta de destruccion principal.

### Banderas Criticas
| **Flag** | **Nombre**      | **Funcion**                                                                        |
| -------- | --------------- | ---------------------------------------------------------------------------------- |
| `-r`     | **Recursive**   | Entra en carpetas y borra todo lo de adentro. Obligatorio para borrar directorios. |
| `-f`     | **Force**       | No pide confirmacion y no da errores si el archivo no existe.                      |
| `-i`     | **Interactive** | Te pregunta archivo por archivo "¿Seguro?". **Usalo siempre al aprender.**         |
| `-v`     | **Verbose**     | Te muestra en pantalla lo que esta borrando.                                       |
### Niveles de Peligro

1. **Nivel Bajo:** Borrar un archivo.
rm archivo.txt

2. **Nivel Medio:** Borrar una carpeta y su contenido.
rm -r carpeta_proyectos/

3. **Nivel Nuclear:** El comando mas peligroso de Linux.
rm -rf / # Intenta borrar TODO el disco duro. Nunca lo ejecutes
