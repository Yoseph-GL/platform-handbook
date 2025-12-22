# Gestion de Procesos: ps, kill, top

Debes saber como monitorear el consumo de recursos y como detener programas que se han colgado.

## 1. Identificando Procesos (PID)
Cada programa tiene un **PID** (Process ID) unico numero.

### ps (Process Status)
Toma una "foto" instantanea de los procesos.

```
# El comando estandar para ver TODO
ps aux

# a = todos los usuarios
# u = mostrar usuario dueño
# x = procesos sin terminal (daemons)
```

Filtrar con grep:

# Muestra solo scripts de python corriendo.
ps aux | grep python

## 2. Monitoreo en Tiempo Real

### top / htop

Muestra CPU, RAM y procesos activos actualizandose cada segundo.

- **top:** Viene instalado en todos lados. Feo pero funcional.
    
- **htop:** Mas moderno, con colores y barras. (Instalar con `sudo apt install htop`).
    
- Salir con `q` o `Ctrl+C`.
    

## 3. Matar Procesos (kill)

Para detener un proceso, necesitas su PID.

**Sintaxis:** `kill [señal] [PID]`

| **Señal**   | **Numero** | **Descripcion**    | **Analogia**                                      |
| ----------- | ---------- | ------------------ | ------------------------------------------------- |
| **SIGTERM** | `-15`      | Terminacion suave. | "Por favor, cierra y guarda tus cosas". (Default) |
| **SIGKILL** | `-9`       | Matanza inmediata. | Desenchufar el cable. El proceso no guarda nada.  |

Ejemplos:
# Intento amable (PID 1234)
kill 1234

# Forzado (si no responde)
kill -9 1234

# Matar por NOMBRE (cuidado, mata todos los que se llamen igual)
pkill nginx
killall apache2