# Arrays (Arreglos) y Listas

Olvida las variables tipo `servidor1`, `servidor2`. Usa estructuras de datos reales.

## 1. Arrays Indexados (Listas simples)
Indices numericos, empezando en 0.

### Declaracion
No uses comas. Usa espacios.
```
frutas=("Manzana" "Banana" "Uva")
```

### Acceso a Datos

La sintaxis requiere llaves `{}`.

| Sintaxis        | Resultado                                   |
| --------------- | ------------------------------------------- |
| `${frutas[0]}`  | Primer elemento ("Manzana").                |
| `${frutas[@]}`  | **Todos** los elementos (usar para bucles). |
| `${#frutas[@]}` | **Longitud**: Cuantos elementos hay (3).    |
| `${!frutas[@]}` | Indices: Devuelve "0 1 2".                  |
|                 |                                             |

### Iteracion (Bucle For)
for fruta in "${frutas[@]}"; do
    echo "Me gusta la $fruta"
done

## 2. Agregar elementos
frutas+=("Naranja")

## 3. Arrays Asociativos (Diccionarios)

Clave-Valor (Como un Dictionary en Python o Map en Java). _Requiere Bash 4.0+_
declare -A usuario usuario[nombre]="Ana" usuario[rol]="Admin" echo "El usuario ${usuario[nombre]} es ${usuario[rol]}"