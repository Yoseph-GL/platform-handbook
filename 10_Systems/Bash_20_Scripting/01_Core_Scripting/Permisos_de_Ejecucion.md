# Permisos de Ejecucion

Por seguridad, Linux crea los archivos nuevos como "No Ejecutables" (rw-r--r--). Para correr un script, debes "armarlo".

## El Bit de Ejecucion (+x)

Si intentas correr un script nuevo:
```
./mi_script.sh
# Error: Permission denied
```

Solucion:
chmod +x mi_script.sh

Esto cambia los permisos a `rwxr-xr-x` (755), permitiendo que el kernel lo inicie como un programa.

## Formas de Ejecutar

### 1. Ruta Relativa (Requiere +x)

Es la forma estandar. El `./` es obligatorio por seguridad (para no ejecutar accidentalmente un virus que se llame igual que un comando del sistema).
./install.sh

### 2. Invocacion Explicita (No requiere +x)

Llamas al interprete y le pasas el archivo como argumento. Ignora los permisos.
bash install.sh
