# Busqueda de Archivos: find

`find` busca archivos basandose en sus metadatos (nombre, tamaño, fecha, dueño), NO en su contenido.

**Sintaxis:** `find [donde_buscar] [criterio] [accion_opcional]`

## 1. Busqueda por Nombre

Es "Case Sensitive" (sensible a mayusculas) por defecto.

```
# Buscar en la carpeta actual (.) archivos que terminen en .conf
find . -name "*.conf"

# Buscar sin importar mayusculas/minusculas (-iname)
find /home -iname "foto.jpg"
```
## 2. Busqueda por Tipo

Filtrar si buscas carpetas o archivos.

find . -type d  # Solo Directorios
find . -type f  # Solo Files (archivos)
find . -type l  # Solo Links

## 3. Busqueda por Tamaño y Tiempo (Admin Power)

Ideal para limpiar discos llenos.

# Archivos mayores a 100 Megabytes
find /var -size +100M

# Archivos modificados en los ultimos 7 dias (-mtime)
find . -mtime -7

# Archivos modificados hace MAS de 30 dias
find /var/log -mtime +30

## 4. Ejecutar acciones (Batch)

Encontrar archivos y hacerles algo inmediatamente.

# Borrar todos los archivos .tmp en todo el sistema (CUIDADO)
find . -name "*.tmp" -delete

# Cambiar permisos a todos los archivos .sh encontrados
find . -name "*.sh" -exec chmod +x {} \;