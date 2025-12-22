# El Comando Test: `[ ]` vs `[[ ]]`

Lo que escribes despues de un `if` no es magia, es un comando. `[` es literalmente un programa en `/usr/bin/[`.

## 1. El Clasico `[ ... ]` (POSIX)
Es el estandar antiguo. Es estricto y propenso a errores si no entrecomillas las variables.

```
if [ -f "$archivo" ]; then ...
```

## 2. El Moderno `[[ ... ]]` (Bash Extension)

Es una palabra clave (keyword) de Bash. Es mucho mas inteligente y seguro.

**Ventajas de `[[ ]]`:**

- No necesitas comillas para variables vacias.
    
- Soporta `&&` y `||` dentro de los corchetes.
    
- Soporta coincidencia de patrones (Regex) con `=~`.
- # Comparacion con Regex (Solo funciona en [[ ]])
if [[ "$email" =~ @gmail.com$ ]]; then
    echo "Es un gmail"
fi

**Veredicto Senior:** Usa **SIEMPRE** `[[ ... ]]` a menos que estes escribiendo para `sh` (Alpine Linux/Embedded) donde `[[` no existe.

## 3. Chequeos de Archivos (File Tests)

| Flag | Pregunta                                       |
| ---- | ---------------------------------------------- |
| `-f` | ¿Existe y es un archivo regular?               |
| `-d` | ¿Existe y es un directorio?                    |
| `-s` | ¿Existe y pesa mas de 0 bytes (no esta vacio)? |
| `-x` | ¿Es ejecutable?                                |
| `-w` | ¿Es escribible?                                |