# Diagnostico de Red: ip y ping

¿El servidor tiene internet? ¿Cual es mi IP? ¿El DNS funciona?

## 1. Ver mi IP (`ip` vs `ifconfig`)
El comando `ifconfig` es obsoleto (deprecated). Usa `ip`.

```
# Mostrar interfaces y direcciones IP
ip a
# Busca "inet" bajo "eth0" o "wlan0".
```

## 2. Prueba de Conectividad: ping

Envia paquetes ICMP para ver si otro equipo responde.

# Ping infinito (Cortar con Ctrl+C)
ping google.com

# Ping limitado a 4 paquetes (Recomendado en scripts)
ping -c 4 8.8.8.8

> **Diagnostico Paso a Paso:**
> 
> 1. `ping 127.0.0.1` (¿Funciona mi tarjeta de red?)
>     
> 2. `ping 192.168.1.1` (¿Llego al router/gateway?)
>     
> 3. `ping 8.8.8.8` (¿Tengo salida a internet?)
>     
> 4. `ping google.com` (¿Funciona el DNS?)
>     

## 3. Puertos y Servicios (netstat / ss)

¿Quien esta escuchando en el puerto 80?
# ss es el reemplazo moderno de netstat
ss -tulanp

- `-t`: TCP
    
- `-u`: UDP
    
- `-l`: Listening (escuchando)
    
- `-n`: Numerico (muestra puertos, no nombres)
    
- `-p`: Proceso (que programa usa el puerto)