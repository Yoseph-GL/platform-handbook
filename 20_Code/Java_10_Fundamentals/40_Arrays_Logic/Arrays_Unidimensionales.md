# Arrays Unidimensionales (Vectores)

Un Array es una estructura de datos estática que almacena múltiples valores del **mismo tipo** en un solo bloque de memoria contiguo.

## 1. Declaración e Inicialización

Tienes 3 formas de crear un array.

```java
// Forma 1: Declarar primero, instanciar después (con tamaño fijo)
int[] numeros;
numeros = new int[5]; // Crea array de 5 espacios llenos de ceros

// Forma 2: Todo en una línea
String[] nombres = new String[3];

// Forma 3: Inicialización literal (Cuando ya sabes los datos)
int[] edades = {18, 25, 30, 40};
// Java infiere que el tamaño es 4.
```

## 2. Valores por Defecto

Cuando creas un array con `new`, Java lo llena automáticamente:

- `int`, `byte`, `short` -> `0`
    
- `double` -> `0.0`
    
- `boolean` -> `false`
    
- `Objetos` (String) -> `null`

## 3. Acceso y Modificación

Los índices empiezan en **0**.
```java
int[] puntajes = new int[3];

puntajes[0] = 100; // Asignar
puntajes[1] = 200;

System.out.println(puntajes[0]); // 100
System.out.println(puntajes[2]); // 0 (Valor por defecto)
```

## 4. Errores Comunes

### A. Imprimir el Array Directamente

Si haces `System.out.println(puntajes)`, verás basura como `[I@1b6d3586`.

- **Razón:** Estás imprimiendo la **dirección de memoria**, no el contenido.
    
- **Solución:** Usa un bucle o `Arrays.toString()`.

### B. ArrayIndexOutOfBoundsException

El error más famoso. Ocurre si intentas acceder a una posición que no existe.
```java
int[] datos = {10, 20}; // Indices validos: 0 y 1
System.out.println(datos[2]); // ERROR FATAL. El programa se detiene.
```

### C. Length es una Propiedad, no un Método

- En Strings: `texto.length()` (con paréntesis).
    
- En Arrays: `array.length` (sin paréntesis).