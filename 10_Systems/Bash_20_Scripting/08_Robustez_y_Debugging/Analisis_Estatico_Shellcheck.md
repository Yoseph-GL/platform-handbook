# ShellCheck: Tu Corrector Automatico

Bash tiene una sintaxis traicionera. ShellCheck es una herramienta externa que analiza tu codigo y encuentra errores logicos y de seguridad **antes** de que ejecutes nada.

Es el estandar de la industria. No subas codigo sin pasarlo por ShellCheck.

## 1. Como usarlo

### Web
Pega tu codigo en [shellcheck.net](https://www.shellcheck.net).

### VS Code (Obligatorio)
Instala la extension **"ShellCheck"**. Subrayara errores en tiempo real (lineas amarillas/rojas).

### Terminal (Linter)
```
# Instalar
sudo apt install shellcheck

# Ejecutar
shellcheck mi_script.sh
```

## 2. Errores Comunes que detecta

**Error 1: Variables sin comillas**
rm $archivo  # ShellCheck: SC2086: Double quote to prevent globbing and word splitting.

Error 2: Uso incorrecto de if
if [ $var = "foo" ] # ShellCheck te sugerira usar [[ ]] y poner comillas.

Error 3: Asignacion con espacios
var = "hola" # ShellCheck: SC1068: Don't put spaces around the = in assignments.