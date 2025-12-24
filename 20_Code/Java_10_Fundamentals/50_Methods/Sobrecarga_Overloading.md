# Sobrecarga de Métodos (Overloading)

Java permite tener múltiples métodos con el **MISMO NOMBRE**, siempre que tengan **DIFERENTES PARÁMETROS**.

## 1. ¿Por qué Sobrecargar?
Para dar flexibilidad al programador. Imagina tener que recordar `imprimirTexto()`, `imprimirNumero()`, `imprimirBoolean()`. Es mejor tener solo `imprimir()` y que Java decida cuál usar.

## 2. Reglas de la Firma
La JVM distingue los métodos por su **Firma**: `Nombre` + `Lista de Tipos de Parámetros`.

* **Válido:** Cambiar cantidad de parámetros.
* **Válido:** Cambiar tipos de parámetros.
* **Válido:** Cambiar el orden de los tipos.
* **INVÁLIDO:** Cambiar solo el tipo de retorno. La JVM no sabe qué método llamar solo por lo que devuelve.

## 3. Ejemplo Práctico

```java
public class Calculadora {

    // Version 1: Dos enteros
    public static int sumar(int a, int b) {
        System.out.println("Usando version INT");
        return a + b;
    }

    // Version 2: Tres enteros (Sobrecarga por cantidad)
    public static int sumar(int a, int b, int c) {
        return a + b + c;
    }

    // Version 3: Dos decimales (Sobrecarga por tipo)
    public static double sumar(double a, double b) {
        System.out.println("Usando version DOUBLE");
        return a + b;
    }

    public static void main(String[] args) {
        sumar(10, 20);      // Llama a V1
        sumar(10, 20, 30);  // Llama a V2
        sumar(5.5, 2.1);    // Llama a V3
        
        // sumar(10); // ERROR: No existe metodo sumar con 1 parametro
    }
}
```

