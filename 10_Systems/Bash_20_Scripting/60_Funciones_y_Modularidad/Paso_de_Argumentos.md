# Argumentos y Valores de Retorno

Bash no usa `func(arg1, arg2)`. Las funciones se comportan como "mini-scripts" dentro del script.

## 1. Recibir Argumentos
Dentro de la funcion, las variables `$1`, `$2`, `$@` cambian de significado. Ahora representan los argumentos **de la funcion**, no del script.

```
crear_usuario() {
    local usuario=$1
    local grupo=$2
    
    if [[ -z "$usuario" ]]; then
        echo "Error: Falta nombre de usuario"
        return 1
    fi
    
    echo "Creando usuario $usuario en grupo $grupo"
}

# Llamada a la funcion (espacios, no comas)
crear_usuario "juan" "devs"
```

## 2. Retornar Valores (El gran malentendido)

En lenguajes normales: `return "Resultado"`. En Bash, `return` SOLO devuelve un **Numero de Estado (0-255)**.

### Caso A: Retornar Exito/Fallo (Status)

Usa `return`.
es_root() {
    if [[ $UID -eq 0 ]]; then
        return 0 # True
    else
        return 1 # False
    fi
}

if es_root; then
    echo "Eres Dios"
fi

### Caso B: Retornar Datos (Strings/Numeros)

Usa `echo` dentro de la funcion y **captura** la salida al llamarla.
obtener_fecha() {
    date +%F
}

# Capturamos el "echo" en una variable
hoy=$(obtener_fecha)
echo "El reporte es de fecha: $hoy"