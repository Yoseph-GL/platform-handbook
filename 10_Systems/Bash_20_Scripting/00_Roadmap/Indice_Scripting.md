# Roadmap: Bash 201 - Scripting & Automation

## 1. Core Scripting
Objetivo: Entender como el kernel ejecuta un archivo de texto como programa.
- [ ] [[El_Shebang]] | Por que `#!/bin/bash` es obligatorio.
- [ ] [[Permisos_de_Ejecucion]] | `chmod +x` y seguridad.
- [ ] [[Modos_de_Ejecucion_Source_vs_Bash]] | Diferencia vital entre correr en sub-shell o shell actual.

## 2. Variables y Tipos de Datos
Objetivo: Manejo de informacion y memoria.
- [ ] [[Scope_Local_vs_Global]] | Evitar colisiones de nombres en scripts largos.
- [ ] [[Arrays_y_Listas]] | Manejar grupos de datos (servidores, archivos).
- [ ] [[Expansion_de_Parametros]] | Magia con `${var:-default}` y `${var%text}`.
- [ ] [[Aritmetica_Basica]] | Operaciones matematicas `((...))`.
- [ ] [[Entrecomillado_Quotes]] | La diferencia critica entre `' '` y `" "`.

## 3. Logica y Control
Objetivo: Toma de decisiones automatizada.
- [ ] [[Exit_Codes_y_Return]] | Entender `$?` y el exito/fracaso (0 vs no-0).
- [ ] [[Test_Operadores_Corchetes]] | Por que usar `[[ ... ]]` es mejor que `[ ... ]`.
- [ ] [[Sentencia_If_Else]] | Estructuras condicionales.
- [ ] [[Sentencia_Case]] | Switch/Case para menus y opciones.
- [ ] [[Operadores_Logicos_AND_OR]] | Short-circuiting `&&` y `||`.

## 4. Bucles e Iteracion
Objetivo: Procesamiento por lotes (Batch processing).
- [ ] [[Bucle_For_Style_C_vs_List]] | Iterar rangos vs iterar listas.
- [ ] [[Bucle_While_y_Until]] | Loops basados en condiciones/demonios.
- [ ] [[Control_Break_y_Continue]] | Saltar pasos o romper ciclos.
- [ ] [[Iterar_Archivos_y_Lineas]] | Patron seguro para leer archivos linea a linea.

## 5. Inputs y Argumentos
Objetivo: Crear herramientas CLI interactivas.
- [ ] [[Argumentos_Posicionales]] | Recibir datos al ejecutar (`$1`, `$2`).
- [ ] [[Comando_read_User_Input]] | Pedir datos al usuario interactivamente.
- [ ] [[Flags_con_Getopts]] | Crear scripts pro (`./deploy.sh -v -f config`).
- [ ] [[Heredocs]] | Inyectar bloques de texto o configuraciones multilineas.

## 6. Funciones y Modularidad
Objetivo: DRY (Don't Repeat Yourself) y librerias.
- [ ] [[Sintaxis_y_Definicion]] | Estructura `function nombre() {}`.
- [ ] [[Paso_de_Argumentos]] | Como pasar parametros a funciones.
- [ ] [[Librerias_y_Sourcing]] | Importar funciones desde otros archivos.

## 7. Herramientas de Texto (Text Processing)
Objetivo: Manipular logs, CSVs y outputs de comandos.
- [ ] [[Manipulacion_con_sed]] | Reemplazo y filtrado de streams.
- [ ] [[Reportes_con_awk]] | Procesamiento de columnas y calculos.
- [ ] [[Corte_con_cut_y_tr]] | Extraccion simple y traduccion de caracteres.
- [ ] [[Regex_Basico]] | Expresiones regulares para validaciones.

## 8. Robustez y Debugging (CRITICO)
Objetivo: Bash Defensivo. Scripts a prueba de balas.
- [ ] [[Unofficial_Strict_Mode]] | Detener ejecucion si algo falla.
- [ ] [[Traps_y_Limpieza]] | Limpiar temporales al salir o cancelar (Ctrl+C).
- [ ] [[Debugging_set_x]] | Trazar la ejecucion para encontrar bugs.
- [ ] [[Analisis_Estatico_Shellcheck]] | Asegurar que los inputs existen.

## 9. Automatizacion y Sistema
Objetivo: Integracion con el OS.
- [ ] [[Cron_Jobs]] | Agendar tareas recurrentes.
- [ ] [[Interaccion_con_Logs]] | Escribir en syslog o archivos de rotacion.
- [ ] [[Scripts_de_Backup]] | Ejemplo real de automatizacion.