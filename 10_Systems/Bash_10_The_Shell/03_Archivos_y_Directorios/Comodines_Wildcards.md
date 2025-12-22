# Comodines (Wildcards) y Globbing

Los comodines permiten seleccionar multiples archivos basandose en patrones de texto. Son vitales para operaciones masivas ("Batch processing").

## Los 3 Grandes

### 1. El Asterisco `*`
Representa **CUALQUIER** cantidad de caracteres (incluyendo cero).

* `ls *.jpg` -> Lista todos los archivos que terminan en .jpg
* `rm config*` -> Borra `config.xml`, `config_v2.txt`, `configuracion.json`.
* `cp app.* /backup` -> Copia `app.js`, `app.css`, `app.html` (mismo nombre, cualquier extension).

### 2. El Signo de Interrogacion `?`
Representa **EXACTAMENTE UN** caracter.

* `ls image_?.png`
    * Match: `image_1.png`, `image_a.png`
    * No Match: `image_10.png` (tiene 2 caracteres)

### 3. Los Corchetes `[ ]`
Representa un **RANGO** o lista especifica de caracteres.

* `rm log_[1-3].txt` -> Borra `log_1.txt`, `log_2.txt`, `log_3.txt`.
* `ls version_[A,B].info` -> Lista solo versiones A o B.

## Brace Expansion (Expansion de llaves) `{}`

No es estrictamente un wildcard (porque lo procesa la shell antes de buscar archivos), pero es muy util para generar nombres.

```bash
# Crear estructura de proyecto rapido
mkdir -p proyecto/{src,dist,test,assets}

# Crear backup con fecha rapida
cp app.js app.js.{bak,old}