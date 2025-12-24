# Variables y Tipos de Datos (Primitivos)

Java es **Estáticamente Tipado**. Debes declarar el tipo de dato antes de usar la variable. Una vez declarada `int`, no puede guardar un text.

## 1. Declaracion e Inicializacion

```java
// Declaracion
int edad; 

// Asignacion
edad = 25;

// Inicializacion (Todo en uno)
int puntos = 100;
```

## 2. Tipos Primitivos (Los 8 Fantasticos)

Estos tipos guardan el **valor** directamente en la memoria Stack. Son rapidos y ligeros.

| Tipo        | Bits | Rango / Uso                      | Ejemplo                  |
| ----------- | ---- | -------------------------------- | ------------------------ |
| **byte**    | 8    | -128 a 127 (Ahorro memoria)      | `byte b = 100;`          |
| **short**   | 16   | Numeros pequeños                 | `short s = 30000;`       |
| **int**     | 32   | **Estandar para enteros**        | `int i = 100000;`        |
| **long**    | 64   | Enteros gigantes (Usa sufijo L)  | `long l = 999999999L;`   |
| **float**   | 32   | Decimales simples (Usa sufijo F) | `float f = 3.14F;`       |
| **double**  | 64   | **Estandar para decimales**      | `double d = 3.14159;`    |
| **boolean** | 1    | `true` o `false` (Logica)        | `boolean activo = true;` |
| **char**    | 16   | Un solo caracter Unicode         | `char letra = 'A';`      |

**Ojo con `char`:** Usa comillas simples `' '`. **Ojo con `String`:** NO es primitivo, es un Objeto. Usa comillas dobles `" "`.

## 3. Inferencia de Tipos (Java 10+)

Puedes usar `var` si el compilador puede adivinar el tipo.

```java
var nombre = "Juan"; // Infiere String
var edad = 20;       // Infiere int
// nombre = 20;      // ERROR: Sigue siendo String internamente.
```

