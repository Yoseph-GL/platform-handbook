# Iteracion Segura: Archivos y Lineas

Este es el error #1 de los novatos: intentar leer lineas de un archivo usando un `for`.

## 1. El Anti-Patron (NO HAGAS ESTO)

```
# MAL
for linea in $(cat archivo.txt); do
    echo "$linea"
done
```

- **Por que falla:** El `for` separa por ESPACIOS, no por lineas. Si una linea dice "Hola Mundo", el loop correra 2 veces: una para "Hola" y otra para "Mundo".
    

## 2. La Forma Correcta: While Read

Para leer un archivo linea por linea respetando espacios.
# BIEN
while IFS= read -r linea; do
    echo "Procesando: $linea"
done < archivo.txt

- `IFS=` : Evita que Bash recorte espacios al inicio/final de la linea.
    
- `-r`: Evita que las barras invertidas `\` se interpreten como escapes.
    
- `< archivo.txt`: Redirecciona el archivo al loop.

## 3. Iterar Archivos en un Directorio (Globbing)

Para procesar archivos, usa siempre el comodin `*` directo en el `for`.
# BIEN: Maneja espacios en nombres de archivo (ej: "mi foto.jpg")
for archivo in *.jpg; do
    mv "$archivo" "procesado_$archivo"
done