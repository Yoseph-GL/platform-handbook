# Manejo de Señales: trap

¿Que pasa si tu script crea archivos temporales y el usuario presiona `Ctrl + C` a la mitad? Los archivos basura se quedan ahi para siempre.
`trap` te permite "atrapar" esas señales y limpiar antes de morir.

## 1. Señales Comunes

| Señal | Nombre | Causa |
|:---|:---|:---|
| `SIGINT` | Interrupt | Usuario presiona `Ctrl + C`. |
| `SIGTERM` | Terminate | El sistema pide detenerse (ej: `kill PID`). |
| `EXIT` | Exit | El script termina (ya sea bien o por error). **Esta atrapa todo.** |

## 2. Patron de Limpieza (Cleanup)

Define una funcion de limpieza y registrala al principio del script.

```
#!/bin/bash

# Carpeta temporal
TEMP_DIR=$(mktemp -d)

# Funcion de limpieza
cleanup() {
    echo "Limpiando basura en $TEMP_DIR..."
    rm -rf "$TEMP_DIR"
}

# REGISTRAR LA TRAMPA (Ejecutar cleanup al salir por CUALQUIER razon)
trap cleanup EXIT

echo "Trabajando..."
touch "$TEMP_DIR/basura.txt"
sleep 10 # Si presionas Ctrl+C aqui, cleanup se ejecutara igual.
```

**Nota:** `trap` es vital para scripts que manejan bloqueos (locks) o credenciales temporales.