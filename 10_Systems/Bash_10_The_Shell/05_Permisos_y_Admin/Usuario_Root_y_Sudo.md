# Superusuario: Root y Sudo

En Linux, no todos los usuarios son iguales. Existe un sistema jerarquico estricto para proteger el sistema de errores humanos y ataques.

## 1. El Usuario Root
Es el dios del sistema.
* **UID (User ID):** 0.
* **Poderes:** Puede leer, modificar y borrar CUALQUIER archivo, sin importar los permisos. Puede matar cualquier proceso.
* **Riesgo:** Un comando mal escrito como root puede destruir el OS en milisegundos.

## 2. El comando sudo (SuperUser DO)
Permite a un usuario normal ejecutar comandos con privilegios de root temporalmente.
Es la forma segura de administrar.

```
# Sintaxis: sudo [comando]
sudo apt update
sudo reboot
```

- **Logs:** Todo comando ejecutado con `sudo` queda registrado en `/var/log/auth.log`.
    
- **Password:** Te pedira TU contraseña, no la de root. Tiene un timeout (usualmente 15 min) antes de volver a pedirla.
- 
## 3. Cambiar de Usuario (su)

A veces necesitas convertirte en otro usuario (ej: postgres, www-data) para depurar.

# Convertirse en root (requiere password de root)
su -
# Convertirse en otro usuario
sudo su - nombre_usuario

**Nota de Seguridad:** Nunca habilites el login directo de `root` por SSH. Usa siempre usuarios normales y escala privilegios con `sudo`.