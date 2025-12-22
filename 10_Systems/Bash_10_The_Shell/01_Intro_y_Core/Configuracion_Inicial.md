# Configuracion Inicial y Atajos

Una terminal sin configurar es ineficiente. Aquí aprenderas a personalizar tu entorno y moverte sin usar el mouse.

## 1. Archivos de Inicio (Dotfiles)

Linux usa archivos ocultos (empiezan con `.`) para guardar configuraciones de usuario. El mas importante para Bash es el `.bashrc`.

* **Ubicacion:** `~/.bashrc` (en tu carpeta Home).
* **Funcion:** Se ejecuta CADA VEZ que abres una terminal nueva.

### Flujo de Edicion
Para modificar tu configuracion:

1.  Abrir archivo: `nano ~/.bashrc`
2.  Editar (añadir alias, variables).
3.  Guardar: `Ctrl+O`, `Enter`.
4.  Salir: `Ctrl+X`.
5.  **Recargar (Importante):** `source ~/.bashrc`

## 2. Alias: Tus primeros atajos

Los alias convierten comandos largos y complejos en palabras cortas. Copia estos en tu `.bashrc` al final del archivo.

# --- ALIAS UTILES ---

# 1. Seguridad: Preguntar antes de sobreescribir/borrar
alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'

# 2. Listados mejores
alias ll='ls -la'       # Listado largo, ocultos y detalles
alias l='ls -CF'        # Listado simple clasificado

# 3. Navegacion rapida
alias ..='cd ..'
alias ...='cd ../..'
alias casa='cd ~'

# 4. Sistema (Ejemplo para Debian/Ubuntu)
alias update='sudo apt update && sudo apt upgrade -y'
alias puertos='netstat -tulanp'

## Atajos

| **Atajo**    | **Nombre**        | **Accion**                                                                         |
| ------------ | ----------------- | ---------------------------------------------------------------------------------- |
| **TAB**      | **Autocompletar** | La tecla mas importante. Escribe `cd Doc` + `TAB` -> `cd Documentos/`.             |
| **Ctrl + L** | Clear             | Limpia la pantalla.                                                                |
| **Ctrl + C** | SIGINT            | **Cancela/Mata** el comando actual.                                                |
| **Ctrl + D** | EOF               | Cierra la sesion (Logout/Exit).                                                    |
| **Ctrl + A** | Home              | Mueve el cursor al **inicio** de la linea.                                         |
| **Ctrl + E** | End               | Mueve el cursor al **final** de la linea.                                          |
| **Ctrl + U** | Cut Line          | Borra todo desde el cursor hacia atras (limpiar password mal escrito).             |
| **Ctrl + R** | Reverse Search    | **Buscador historico.** Empieza a escribir un comando que usaste ayer y aparecera. |
