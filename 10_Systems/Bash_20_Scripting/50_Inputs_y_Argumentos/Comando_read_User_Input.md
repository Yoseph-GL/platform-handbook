# Interaccion con el Usuario: read

Permite pausar la ejecucion y pedir datos por teclado. Ideal para scripts de configuracion interactiva ("wizards").

## 1. Sintaxis Basica
```
echo "Ingresa tu nombre:"
read nombre
echo "Hola $nombre"
```

## 2. Banderas Utiles

Para no escribir `echo` antes, usa `-p`.

| Flag | Funcion                                             | Ejemplo                         |
| ---- | --------------------------------------------------- | ------------------------------- |
| `-p` | **Prompt:** Muestra texto antes de esperar input.   | `read -p "Usuario: " user`      |
| `-s` | **Silent:** No muestra lo que escribes (Passwords). | `read -s -p "Password: " pass`  |
| `-t` | **Timeout:** Espera X segundos y si no, continua.   | `read -t 5 -p "Continuar? " op` |
| `-n` | **Nchars:** Lee N caracteres y termina (sin Enter). | `read -n 1 -p "Si/No: " res`    |

## 3. Valores por defecto

Bash no tiene flag de "default", pero puedes usar logica de variables.
read -p "Ingresa IP [127.0.0.1]: " ip_input
ip_address=${ip_input:-"127.0.0.1"}
echo "Conectando a $ip_address"