# Scope: Variables Locales vs Globales

En Bash, por defecto, **TODAS las variables son GLOBALES**, incluso si se definen dentro de una función. Esto es peligroso porque puedes sobrescribir datos sin querer.

## 1. El Problema Global

```
#!/bin/bash

nombre="Juan"

cambiar_nombre() {
    nombre="Pedro"  # Sobrescribe la variable global
}

cambiar_nombre
echo $nombre
# Salida: Pedro (¡La variable original se perdio!)
```

## 2. La Solucion: `local`

Dentro de las funciones, usa SIEMPRE la palabra clave `local`. Esto confina la variable a esa funcion solamente.
#!/bin/bash

nombre="Juan"

cambiar_nombre_seguro() {
    local nombre="Pedro" # Esta es una variable nueva, solo vive aqui
    echo "Dentro de la funcion: $nombre"
}

cambiar_nombre_seguro
echo "Fuera de la funcion: $nombre"
# Salida:
# Dentro de la funcion: Pedro
# Fuera de la funcion: Juan (Intacta)

**Regla de Oro:** Nunca uses variables globales dentro de funciones a menos que sea estrictamente necesario (ej: configuración general). Usa `local` para todo lo demas.