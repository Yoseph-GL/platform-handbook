# Conexion Segura: SSH (Secure Shell)

SSH es el protocolo estandar para administrar servidores Linux de forma remota. Todo el trafico viaja encriptado.

## 1. Comando Basico
Para conectarte a otro equipo:

```
# Sintaxis: ssh usuario@direccion_ip
ssh root@192.168.1.50
```

Si es la primera vez, te pedira confirmar la "huella" (fingerprint) del servidor. Escribe `yes`.

## 2. Autenticacion con Llaves (Key-Based Auth)

Escribir contraseñas es inseguro y lento. Los profesionales usan pares de llaves criptograficas.

### A. Generar llaves (En tu PC local)
ssh-keygen -t rsa -b 4096
# Presiona Enter a todo. Creara dos archivos en ~/.ssh/
# id_rsa (Llave PRIVADA - NUNCA la compartas)
# id_rsa.pub (Llave PUBLICA - Se sube al servidor)

### B. Copiar llave al servidor

Este comando instala tu llave publica en el servidor remoto automaticamente.
ssh-copy-id usuario@192.168.1.50
Ahora podras entrar sin password.

## 3. Config (Truco Pro)

Si administras muchos servidores, no memorices IPs. Crea un archivo `~/.ssh/config`:
Host web-prod
    HostName 203.0.113.5
    User admin
    IdentityFile ~/.ssh/id_rsa

Host db-dev
    HostName 10.0.0.5
    User postgres
    
Ahora solo escribes: `ssh web-prod`.

> **Permisos Criticos:** SSH es paranoico con los permisos. Si tus llaves estan muy abiertas, fallara. `chmod 700 ~/.ssh` `chmod 600 ~/.ssh/id_rsa`

