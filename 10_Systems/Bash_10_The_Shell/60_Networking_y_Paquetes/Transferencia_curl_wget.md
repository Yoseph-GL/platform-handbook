# Transferencia de Datos: curl y wget

En un servidor sin interfaz grafica, no puedes abrir Chrome para descargar un archivo. Usas estas herramientas.

## 1. wget (World Wide Web Get)
**Uso:** Descargas simples y recursivas de archivos. Es robusto (si se cae internet, reintenta).

```
# Descargar un archivo
wget [https://ejemplo.com/instalador.zip](https://ejemplo.com/instalador.zip)

# Descargar y guardar con otro nombre (-O)
wget -O mi_script.sh [https://ejemplo.com/setup_v2.sh](https://ejemplo.com/setup_v2.sh)
```

## 2. curl (Client URL)

**Uso:** La navaja suiza. Sirve para descargar, pero tambien para probar APIs, ver cabeceras HTTP y debuggear conexiones.

### Descarga Basica
# curl tira el contenido a pantalla por defecto.
# Usa -o (minúscula) o -O (mayúscula) para guardar.
curl -O [https://ejemplo.com/imagen.png](https://ejemplo.com/imagen.png)

Diagnostico HTTP (Para Desarrolladores)
# Ver solo los Headers (-I)
# Util para ver si el servidor responde 200 OK o 404/500
curl -I [https://google.com](https://google.com)

# Modo Verbose (-v)
# Muestra todo el "handshake" TLS y la comunicacion detallada.
curl -v [https://api.miempresa.com](https://api.miempresa.com)

Interaccion con APIs
# Enviar un POST con JSON
curl -X POST -H "Content-Type: application/json" -d '{"login":"user"}' [https://api.com/login](https://api.com/login)

