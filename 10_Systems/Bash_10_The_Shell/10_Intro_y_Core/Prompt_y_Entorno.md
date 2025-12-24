# Anatomia del Prompt y Entorno

El **Prompt** es el indicador visual que espera tus ordenes. Saber leerlo es vital para saber **quien eres**, **donde estas** y **que peligro corres**.

## 1. Decodificando el PS1

El formato estandar se ve asi:
`usuario@hostname:directorio$ `

1.  **Usuario:** El usuario actual (ej: `dev`).
2.  **Hostname:** El nombre del servidor (ej: `aws-prod-01`). Vital para no reiniciar el servidor equivocado.
3.  **Directorio:** Donde estas parado (ej: `~/proyectos`). `~` es tu Home.
4.  **El Simbolo (The Glyph):**
    * `$` : **Usuario Normal.** Tienes permisos limitados. Seguro.
    * `#` : **Usuario Root.** Tienes poder absoluto. **PELIGRO EXTREMO.**

> **Advertencia:** Si ves un `#` al final de tu prompt, piensa dos veces antes de ejecutar `rm` o cambios de configuracion.

## 2. Variables de Entorno

Son valores globales ("constantes") que el sistema operativo y los programas usan para configurarse.

**Comandos para inspeccionar:**

env | less     # Ver todas las variables (paginado)
echo $VARIABLE # Ver el valor de una sola

### Variables Criticas (Top 3)

#### A. `$HOME`

La ruta a tu carpeta personal.

- Valor tipico: `/home/juan`
    
- Equivalente: `~`
    

#### B. `$USER`

Tu nombre de usuario actual. Util para scripts.

#### C. `$PATH` (La mas importante)

Es una lista de carpetas separadas por `:`. Cuando escribes un comando (ej: `python`), la shell busca el ejecutable en estas carpetas, en orden.

echo $PATH
# Salida: /usr/local/bin:/usr/bin:/bin:/usr/sbin

- **Problema comun:** "Command not found".
    
- **Causa:** El programa esta instalado, pero su carpeta no esta en tu `$PATH`.