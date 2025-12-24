# Tecnicas de Debugging (Depuracion)

No llenes tu codigo de `echo "llegue aqui"`. Usa las herramientas nativas.

## 1. El Modo Trace (`-x`)
Imprime en pantalla cada comando **antes** de ejecutarlo, con las variables ya expandidas.

### Opcion A: Todo el script
Ejecuta el script llamando a bash explicitamente con la bandera.
```
bash -x script.sh
```

### Opcion B: Solo un bloque (Dentro del codigo)

Si el script es gigante y solo quieres ver una parte.
echo "Inicio normal"

set -x  # Encender debug
variable="Mundo"
echo "Hola $variable"
set +x  # Apagar debug

echo "Fin normal"

# Salida en consola:
Inicio normal
+ variable=Mundo
+ echo 'Hola Mundo'
Hola Mundo
+ set +x
Fin normal

(Los lineas con `+` son informacion de debug).

## 2. Modo Verbose (`-v`)

Imprime las lineas del script tal cual estan escritas (con comentarios y todo) antes de procesarlas. Menos util que `-x`, pero sirve para encontrar errores de sintaxis.

## 3. Debugging de Variables

Para ver que contiene una variable compleja (como un array) sin ambiguedades, usa `declare -p`.
arr=("uno" "dos")
declare -p arr
# Salida: declare -a arr='([0]="uno" [1]="dos")'