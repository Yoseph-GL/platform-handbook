# El Modo Estricto (Bash Strict Mode)

Por defecto, Bash es muy permisivo: si un comando falla, sigue ejecutando la siguiente linea. Si usas una variable que no existe, la ignora. **Esto es terrible para produccion.**

Debes iniciar tus scripts con esta "Trinidad de la Seguridad".

## La Cabecera Sagrada

Copia esto al inicio de todos tus scripts despues del shebang:

```
#!/bin/bash
set -euo pipefail
```

## Desglose de Banderas

### 1. `set -e` (Exit immediately)

Termina el script inmediatamente si **cualquier** comando devuelve un error (exit code != 0).

- **Sin esto:** El script falla borrando la carpeta equivocada y sigue tratando de copiar archivos ahi. Desastre.
    

### 2. `set -u` (Unset variables)

Termina el script si intentas usar una variable que no has definido.

- **Sin esto:** `rm -rf /$CARPETA_MAL_ESCRITA` se convierte en `rm -rf /` (Borrar todo el sistema).
    

### 3. `set -o pipefail`

Por defecto, en una tuberia (`cmd1 | cmd2`), Bash solo mira el exit code del **ultimo** comando.

- **Sin esto:** `comando_fallido | echo "ok"` devuelve exito (0), porque `echo` funciono, aunque el primero fallo.
    
- **Con esto:** Si cualquier parte del pipe falla, todo falla.
    

## Excepciones (Como permitir fallos controlados)

A veces quieres que un comando falle (ej: `grep` no encuentra nada).
set -e

# Esto detendria el script si no encuentra nada:
# grep "texto" archivo.txt

# Solucion: Forzar exito con OR true
grep "texto" archivo.txt || true