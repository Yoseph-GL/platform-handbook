# Aritmetica en Bash: (( ))

Bash maneja enteros de forma nativa. Para decimales, necesitas ayuda externa.

## 1. El Doble Parentesis (( ... ))
Es la forma moderna y recomendada. Permite espacios y sintaxis estilo C.

```
num=5

# Operacion y asignacion
(( resultado = num + 5 ))

# Incrementar (Estilo C++)
(( num++ ))
(( num+=10 ))

echo $num
```

## 2. Operadores Soportados

- `+`, `-`, `*`, `/` (Division entera), `%` (Modulo/Resto).
    
- `**` (Potencia).
 (( es_par = num % 2 ))
if (( es_par == 0 )); then
    echo "Es par"
fi

## 3. La Limitacion de los Decimales

Bash **NO** sabe sumar `1.5 + 1.5`. Da error de sintaxis.

**Solucion:** Usar `bc` (Basic Calculator) con pipes.
echo "scale=2; 1.5 + 1.5" | bc
# Salida: 3.00