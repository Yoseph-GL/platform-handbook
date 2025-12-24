# Roadmap: Java 01 - Fundamentals & Logic

Este modulo cubre lo esencial para que el lenguaje no sea un obstaculo. No veremos objetos todavia, solo logica pura y manejo de memoria.

## 1. Core Syntax & Environment
Objetivo: Configurar el entorno y entender la estructura basica de un archivo `.java`.
- [ ] [[Configuracion_JDK_y_IDE]] | Instalar OpenJDK e IntelliJ IDEA.
- [ ] [[JVM_JRE_JDK_Diferencias]] | Entender que es lo que ejecuta tu codigo.
- [ ] [[Estructura_Clase_Main]] | `public static void main(String[] args)`.
- [ ] [[Variables_y_Tipos_Primitivos]] | `int`, `double`, `boolean`, `char`.
- [ ] [[Input_Output_Scanner]] | Leer teclado y escribir en consola.

## 2. Memory Primitives (Critico)
Objetivo: Entender donde viven los datos. Diferenciar entre valor y referencia.
- [ ] [[Stack_vs_Heap_Intro]] | La pila de ejecucion vs la memoria dinamica.
- [ ] [[Paso_por_Valor_vs_Referencia]] | ¿Por que mi variable no cambio dentro del metodo?
- [ ] [[Strings_Pool_e_Inmutabilidad]] | Por que `==` no funciona con Strings.
- [ ] [[Casting_Explicito_e_Implicito]] | Convertir `double` a `int` y sus riesgos.

## 3. Control Flow (Logica)
Objetivo: Controlar el flujo de ejecucion.
- [ ] [[Condicionales_If_Else_Ternario]] | Toma de decisiones.
- [ ] [[Switch_Case_y_Yield]] | Estructuras de seleccion multiple modernas.
- [ ] [[Bucles_While_DoWhile]] | Repeticion basada en condiciones.
- [ ] [[Bucles_For_ForEach]] | Repeticion basada en contadores.
- [ ] [[Control_Break_Continue]] | Alterar el flujo de los bucles.

## 4. Arrays & Data
Objetivo: Manejar colecciones de datos de tamaño fijo.
- [ ] [[Arrays_Unidimensionales]] | Vectores basicos `int[]`.
- [ ] [[Arrays_Multidimensionales_Matrices]] | Tablas y matrices `int[][]`.
- [ ] [[Clase_Arrays_Utilities]] | Ordenamiento y busqueda con `java.util.Arrays`.

## 5. Methods & Modularity
Objetivo: Principio DRY (Don't Repeat Yourself).
- [ ] [[Definicion_y_Firma]] | Parametros, retorno y firma del metodo.
- [ ] [[Sobrecarga_Overloading]] | Mismo nombre, diferentes parametros.
- [ ] [[Scope_Alcance_Variables]] | Donde vive y muere una variable.