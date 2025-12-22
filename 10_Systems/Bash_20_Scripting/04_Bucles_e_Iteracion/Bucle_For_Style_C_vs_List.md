# Bucle For: Listas vs Estilo C

En Bash, el bucle `for` tiene dos personalidades. Debes saber cual usar segun la tarea.

## 1. For-In (Iterar Elementos)
Es el mas comun. Recorre una lista de strings, archivos o el resultado de un comando.

**Sintaxis:**
```
for variable in lista_de_cosas; do
    comando
done
```

Ejemplos
# Iterar una lista explicita
for servidor in "web01" "db01" "cache01"; do
    echo "Reiniciando $servidor..."
done

# Iterar rangos (Brace Expansion)
for i in {1..5}; do
    echo "Numero $i"
done

## 2. For Estilo C (Contadores)

Si vienes de C, Java o JS, esto te resultara familiar. Se usa dentro de doble parentesis `(( ))`.

**Sintaxis:** `for (( inicializacion; condicion; incremento ))`
# Contar del 0 al 10 de 2 en 2
for (( i=0; i<=10; i+=2 )); do
    echo "Indice: $i"
done

**Nota:** El estilo C es ideal para calculos matematicos. El estilo "For-In" es ideal para procesar texto y archivos.