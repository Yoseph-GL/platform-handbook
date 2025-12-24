# Filesystem Hierarchy Standard (FHS)

Linux no usa letras de unidad (`C:`, `D:`). Todo nace de una sola raiz: `/`.
La estructura es un arbol invertido estandarizado. Como ingeniero, debes saber donde buscar.

## Mapa del Territorio

```text
/ (Raiz)
├── bin     # Binarios (comandos basicos como ls, cp, cat)
├── boot    # Kernel y arranque (GRUB) - NO TOCAR
├── dev     # Dispositivos (hard drives, terminales, null)
├── etc     # Configuracion del sistema (AQUI vive la config)
├── home    # Carpetas de usuarios (Documentos, Descargas)
├── lib     # Librerias compartidas (como DLLs en Windows)
├── media   # Montajes automaticos (USB, CD)
├── mnt     # Montajes manuales temporales
├── opt     # Software opcional/externo (ej: Chrome, Docker)
├── proc    # Informacion de procesos en tiempo real (Virtual)
├── root    # La casa del superusuario (NO es /home/root)
├── sbin    # Binarios de Sistema (solo para root, ej: reboot)
├── tmp     # Temporales (se borran al reiniciar)
├── usr     # User Programs (software instalado por gestor de paquetes)
└── var     # Variable data (LOGS, webs, bases de datos)
```

## Directorios Criticos para DevOps

| **Ruta**      | **Funcion**       | **Ejemplo de Uso**                           |
| ------------- | ----------------- | -------------------------------------------- |
| **/etc**      | **Configuracion** | `nano /etc/ssh/sshd_config` (Configurar SSH) |
| **/var/log**  | **Logs**          | `tail -f /var/log/syslog` (Ver errores)      |
| **/home**     | **Usuarios**      | `cd /home/juan` (Ir a tus archivos)          |
| **/bin**      | **Comandos**      | Donde viven los programas que ejecutas.      |
| **/dev/null** | **Agujero Negro** | Lo que envias aqui desaparece.               |
