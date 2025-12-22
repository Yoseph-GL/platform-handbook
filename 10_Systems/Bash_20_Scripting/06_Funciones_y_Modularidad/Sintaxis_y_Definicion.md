# Definicion de Funciones

Una funcion es un bloque de codigo con nombre que puedes reutilizar. Bash lee el archivo linea por linea, asi que **debes definir la funcion ANTES de llamarla**.

## 1. Sintaxis
Existen dos formas. La segunda es la mas compatible (POSIX).

```
# Forma 1 (Con palabra clave function)
function saludar {
    echo "Hola"
}

# Forma 2 (Estandar C-Style - RECOMENDADA)
saludar() {
    echo "Hola"
}
```

## 2. Como llamarla

Simplemente escribe su nombre. **NO** uses parentesis `()` al llamarla.
# BIEN
saludar

# MAL
saludar()
call saludar

## 3. Ejemplo de Estructura
#!/bin/bash

# 1. Definiciones primero
instalar_nginx() {
    echo "Instalando..."
    # yum install nginx...
}

configurar_firewall() {
    echo "Configurando..."
}

# 2. Logica principal al final (Main)
echo "Iniciando deployment..."
instalar_nginx
configurar_firewall