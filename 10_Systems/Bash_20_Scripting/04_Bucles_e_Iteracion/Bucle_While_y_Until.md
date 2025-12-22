# Bucles Condicionales: While y Until

Se ejecutan basandose en el estado de un comando o condicion, no en una lista fija.

## 1. While (Mientras)
Ejecuta el bloque **mientras** la condicion sea VERDADERA (Exit code 0).

```
contador=1

while (( contador <= 5 )); do
    echo "Intento $contador"
    (( contador++ ))
done
```

### El Bucle Infinito (Daemons)

Muy usado en scripts que deben correr para siempre (monitores).
while true; do
    echo "Monitoreando sistema..."
    sleep 60  # Pausa de 60 segundos para no quemar CPU
done

## 2. Until (Hasta que)

Es lo opuesto al While. Ejecuta el bloque **mientras** la condicion sea FALSA (Error). Se detiene cuando la condicion se vuelve verdadera.

**Caso de Uso:** Esperar a que un servidor responda.
# "Haz ping HASTA QUE google responda"
until ping -c 1 google.com; do
    echo "Sin internet. Reintentando en 5s..."
    sleep 5
done
echo "Conexion restablecida!"