# Scripts de Backup y Retención

Hacer un backup es fácil (`cp`). Lo difícil es hacerlo automáticamente, ponerle fecha y **borrar los viejos** para no llenar el disco.

## 1. Nombramiento Dinámico (Timestamping)
Nunca sobreescribas el backup anterior. Usa la fecha en el nombre.

```
DESTINO="/mnt/backups"
FECHA=$(date +%Y%m%d_%H%M%S) # Ejemplo: 20231025_143000
ARCHIVO="proyecto_backup_$FECHA.tar.gz"

echo "Creando $ARCHIVO ..."
```

## 2. Compresión con tar

`tar` es el estándar para empaquetar.

- `c`: Crear.
    
- `z`: Comprimir con gzip (rápido).
    
- `f`: Archivo destino.
- # Empaquetar la carpeta /var/www/html
tar -czf "$DESTINO/$ARCHIVO" /var/www/html

## 3. Política de Retención (Borrar viejos)

Aquí entra el comando `find` que vimos en Bash 101. "Busca archivos en la carpeta de backups que sean más viejos que X días y bórralos".
# Borrar archivos .tar.gz modificados hace mas de 7 dias
find "$DESTINO" -name "*.tar.gz" -mtime +7 -delete

# 4. Template Completo (Ejemplo)
#!/bin/bash
set -euo pipefail

BACKUP_DIR="/backups/mysql"
DAYS_TO_KEEP=7
TIMESTAMP=$(date +%F)
FILENAME="db_dump_$TIMESTAMP.sql.gz"

# 1. Crear backup
mysqldump -u root -pSecreto mi_db | gzip > "$BACKUP_DIR/$FILENAME"

# 2. Verificar si se creó
if [[ -f "$BACKUP_DIR/$FILENAME" ]]; then
    logger "Backup DB Exitoso: $FILENAME"
    
    # 3. Limpieza
    find "$BACKUP_DIR" -name "*.sql.gz" -mtime +$DAYS_TO_KEEP -delete
else
    logger -p user.err "Backup DB FALLO"
    exit 1
fi