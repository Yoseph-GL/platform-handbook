# Arquitectura CLI: Terminal, Shell y Kernel

Para dominar Linux, debes entender que "la pantalla negra" no es una sola cosa, sino varias capas de software trabajando juntas.

## 1. El Flujo de Datos (The Layers)

Imagina una cebolla. Cuando escribes un comando, viaja a través de estas capas:

`Usuario` -> `Terminal (GUI)` -> `Shell (Interprete)` -> `Kernel (Nucleo)` -> `Hardware`

### Las Capas Explicadas

1.  **Terminal (El Emulador):**
    * **Que es:** Es solo una ventana grafica. Un "televisor".
    * **Funcion:** Captura tus tecleos y muestra texto en pantalla. No procesa logica.
    * **Ejemplos:** Windows Terminal, iTerm2 (Mac), Alacritty, GNOME Terminal.
    * *Nota: Si cierras la ventana, matas a la Shell que vive adentro.*

2.  **Shell (El Interprete):**
    * **Que es:** El programa que vive DENTRO de la terminal.
    * **Funcion:** Recibe texto ("ls"), lo traduce a instrucciones de sistema y le dice al Kernel qué hacer. Es el cerebro de la linea de comandos.
    * **Ejemplos:** Bash, Zsh, Fish, Sh.

3.  **Kernel (El Nucleo):**
    * **Que es:** El corazon del Sistema Operativo (Linux).
    * **Funcion:** Habla con el hardware (CPU, RAM, Disco). Nadie toca el hardware sin permiso del Kernel.

---

## 2. Tipos de Shell (El Zoo)

Aunque la terminal sea la misma, el interprete (Shell) puede cambiar.

| Shell | Nombre Completo | Uso Principal | Caracteristicas |
|:---|:---|:---|:---|
| **sh** | Bourne Shell | Scripts de Sistema | La original (1977). Muy basica. Estandar en contenedores Docker minimalistas (Alpine). |
| **bash** | Bourne Again Shell | **Estandar Global** | La mas usada en servidores Linux. Compatible y robusta. Es la que aprenderas aqui. |
| **zsh** | Z Shell | Uso Personal | Muy popular en macOS y laptops de desarrolladores. Soporta plugins visuales y autocompletado avanzado. |
| **fish** | Friendly Interactive | Principiantes | Colores y sugerencias automaticas desde el dia 0. No es 100% compatible con Bash. |

> **Comando de Verificacion:**
> Para saber que shell estas usando ahora mismo:
> ```bash
> echo $SHELL
> ```

---

## 3. ¿Por que importa la diferencia? (Caso SSH)

Cuando te conectas a un servidor remoto (ej: AWS, DigitalOcean) usando **SSH**:

1.  Sigues usando tu **Terminal** local (iTerm, Windows Terminal).
2.  Pero ahora estas hablando con la **Shell** del servidor remoto (Bash en Linux).

**Conclusion:** Puedes tener una terminal bonita en Windows, pero estar operando un servidor Linux crudo a traves de la red. Tu terminal es la ventana; la Shell es donde ocurre la accion.