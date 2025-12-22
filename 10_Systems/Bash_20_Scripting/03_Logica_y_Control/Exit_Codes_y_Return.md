# Exit Codes y Return Status

En Bash, las funciones y comandos NO retornan datos (como un string o un objeto). Retornan un **Estado de Exito o Fracaso**.

## 1. La Variable Magica `$?`
Inmediatamente despues de ejecutar CUALQUIER comando, Bash guarda su resultado en `$?`.

* **0 (Cero):** EXITO. El comando funcionó bien. (Counter-intuitivo si vienes de C/Java donde 0 es False).
* **1-255:** ERROR. Algo salio mal.

```
ls /home
echo $?
# Salida: 0 (Todo bien)

ls /carpeta_imaginaria
echo $?
# Salida: 2 (No existe)
```

## 2. Definir tu propio Exit Code

Cuando escribes un script, tu debes decirle al sistema si tu script termino bien o mal usando `exit`.
#!/bin/bash

if [[ -f "config.txt" ]]; then
    echo "Todo listo"
    exit 0  # Terminamos bien
else
    echo "Falta config" >&2
    exit 1  # Terminamos con error
fi

**Importante:** Si no pones `exit` al final, el script retorna el codigo del ULTIMO comando que se ejecuto. Eso es peligroso.

## 3. Return en Funciones

Dentro de una funcion, `exit` mata todo el script. Usa `return` para salir solo de la funcion.

check_user() {
    if [[ "$1" == "root" ]]; then
        return 0 # True / Exito
    else
        return 1 # False / Fallo
    fi
}