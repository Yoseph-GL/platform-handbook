# Glosario Tecnico Linux

Definiciones cortas para conceptos que suelen confundir.

## A
* **Alias:** Apodo corto para un comando largo. Se definen en `.bashrc`.
* **Argumento:** Informacion extra que le das a un comando (ej: en `mkdir fotos`, "fotos" es el argumento).

## B
* **Bash:** "Bourne Again Shell". El interprete de comandos mas popular en Linux.
* **Binario:** Un archivo ejecutable (programa), equivalente al `.exe` de Windows. Usualmente viven en `/bin` o `/usr/bin`.

## D
* **Daemon (Demonio):** Proceso que corre en segundo plano sin interfaz (ej: un servidor web, cron).
* **Distro (Distribucion):** Sabor de Linux (Ubuntu, Fedora, Debian, Alpine). Comparten el Kernel pero cambian las herramientas y gestores de paquetes.

## E
* **Entorno (Environment):** Conjunto de variables (`PATH`, `USER`) que definen el contexto donde corren los programas.

## F
* **Flags (Banderas):** Opciones que modifican un comando, inician con guion (ej: `-r`, `--help`).

## K
* **Kernel:** El nucleo del sistema operativo. Gestiona CPU, RAM y Drivers. Es el jefe de la Shell.

## P
* **PID (Process ID):** Numero unico que identifica a un proceso corriendo.
* **Pipe (Tuberia `|`):** Mecanismo para conectar la salida de un programa con la entrada de otro.
* **Prompt:** El texto a la izquierda del cursor (`user@host:~$`).
* **Path (Ruta):** La direccion de un archivo. Puede ser Absoluta (desde `/`) o Relativa (desde aqui).

## R
* **Recursivo:** Accion que se aplica al directorio padre y desciende a todos sus hijos y nietos (ej: `rm -r`).
* **Root:** El superusuario o administrador del sistema. UID 0.

## S
* **Shell:** Programa que interpreta tus comandos de texto y se los pasa al Kernel.
* **SSH:** Protocolo para operar terminales de forma remota y encriptada.
* **Sudo:** "SuperUser DO". Comando para pedir permisos de administrador temporalmente.

## T
* **Terminal:** La ventana grafica (emulador) que te muestra la Shell.

## W
* **Wildcard (Comodin):** Caracteres especiales (`*`, `?`) usados para seleccionar multiples archivos por patron de nombre.