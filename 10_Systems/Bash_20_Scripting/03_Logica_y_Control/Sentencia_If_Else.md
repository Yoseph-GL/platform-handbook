# Sentencia If-Else

Estructuras de control para bifurcar el flujo del programa.

## 1. Sintaxis Basica
Nota el `then` y el cierre `fi` (if al reves).

```
if [[ condicion ]]; then
    # codigo si es true
elif [[ otra_condicion ]]; then
    # codigo alternativo
else
    # codigo si nada se cumple
fi
```

## 2. Comparadores

### Para Strings (Texto)

| Operador | Significado                |
| -------- | -------------------------- |
| `==`     | Igual a                    |
| `!=`     | Diferente de               |
| `-z`     | String VACIO (Zero length) |
| `-n`     | String NO VACIO (Non-zero) |
if [[ -z "$PASSWORD" ]]; then
    echo "Error: Password vacio"
fi
### Para Numeros (Enteros)

Dentro de `[[ ]]` se usan letras. Dentro de `(( ))` se usan simbolos.

| En `[[ ]]` | En `(( ))` | Significado              |
| ---------- | ---------- | ------------------------ |
| `-eq`      | `==`       | Equal (Igual)            |
| `-ne`      | `!=`       | Not Equal (Diferente)    |
| `-gt`      | `>`        | Greater Than (Mayor que) |
| `-lt`      | `<`        | Less Than (Menor que)    |
| `-ge`      | `>=`       | Mayor o igual            |
| `-le`      | `<=`       | Menor o igual            |
# Estilo clasico
if [[ $edad -ge 18 ]]; then ...

# Estilo moderno (C-Style)
if (( edad >= 18 )); then ...