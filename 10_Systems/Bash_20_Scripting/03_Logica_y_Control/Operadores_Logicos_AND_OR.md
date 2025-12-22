### Archivo 5: `Operadores_Logicos_AND_OR.md`

```
# Operadores Logicos y Short-Circuiting

Puedes encadenar comandos basandote en si el anterior fallo o funciono. Esto hace los scripts compactos y elegantes.

## 1. AND Logico (`&&`)
"Ejecuta el segundo SOLO SI el primero tuvo exito (exit code 0)".

```bash
# Primero crea la carpeta, Y SI PUDO, entra en ella.
mkdir nueva_carpeta && cd nueva_carpeta
```

## 2. OR Logico (`||`)

"Ejecuta el segundo SOLO SI el primero FALLO (exit code != 0)".
# Intenta crear el usuario, O SI FALLA, avisa el error.
useradd juan || echo "Error: El usuario ya existe o no eres root."

## 3. El Patron "One-Liner"

Muy comun en despliegues.
# Descarga && Instala || Avisa error
./download.sh && ./install.sh || echo "El deployment fallo"

## 4. Agrupacion `{ }`

Si quieres ejecutar varios comandos despues de un `||`, agrupalos.
ping -c 1 google.com || {
    echo "Sin internet"
    echo "Abortando..."
    exit 1
}