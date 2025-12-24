# Control de Flujo: Break y Continue

A veces necesitas alterar el comportamiento natural del bucle.

## 1. Break (Romper)
Sale del bucle inmediatamente. Termina la iteracion por completo.

**Ejemplo:** Buscar un archivo y detenerse al encontrarlo.

```
for archivo in *; do
    if [[ "$archivo" == "objetivo.txt" ]]; then
        echo "¡Encontrado!"
        break # Deja de buscar, salta al final del 'done'
    fi
    echo "Revisando $archivo..."
done
```

## 2. Continue (Saltar)

Detiene la iteracion ACTUAL y salta a la SIGUIENTE.

**Ejemplo:** Procesar archivos pero ignorar los `.tmp`.
for archivo in *; do
    if [[ "$archivo" == *.tmp ]]; then
        echo "Saltando temporal: $archivo"
        continue # Vuelve arriba, al siguiente archivo
    fi
    
    # Este codigo solo corre si NO hubo continue
    echo "Procesando $archivo..."
done