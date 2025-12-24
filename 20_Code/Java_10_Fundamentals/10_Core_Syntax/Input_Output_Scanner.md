# Input / Output: Consola y Scanner

Interactuar con el usuario a traves de la terminal.

## 1. Output (Salida)

Imprimir en pantalla. Usamos la clase `System`.

```java
// Imprime y salta linea (ln = line new)
System.out.println("Hola"); 
System.out.println("Mundo");
/* Salida:
Hola
Mundo
*/

// Imprime SIN saltar linea
System.out.print("Hola ");
System.out.print("Mundo");
// Salida: Hola Mundo
```

## 2. Input (Entrada) con Scanner

Para leer del teclado, necesitamos la clase `java.util.Scanner`.
```java
import java.util.Scanner; // Importacion obligatoria

public class Main {
    public static void main(String[] args) {
        // 1. Crear el objeto Scanner conectado a System.in (Teclado)
        Scanner scanner = new Scanner(System.in);

        // 2. Leer Texto
        System.out.print("Tu nombre: ");
        String nombre = scanner.nextLine(); // Lee toda la linea hasta Enter

        // 3. Leer Numeros
        System.out.print("Tu edad: ");
        int edad = scanner.nextInt();

        System.out.println("Hola " + nombre + ", tienes " + edad);
        
        // Buena practica: cerrar scanner al terminar (aunque en consola no es critico)
        scanner.close(); 
    }
}
```

## 3. La Trampa del `nextLine()`

Si usas `nextInt()` y luego `nextLine()`, el programa parecera saltarse la lectura del texto.

**Causa:** `nextInt()` lee el numero pero deja el "Enter" (`\n`) en el buffer. El siguiente `nextLine()` lee ese Enter y cree que el usuario envio una linea vacia.

**Solucion:** Consumir el salto de linea sobrante.
```java
int edad = scanner.nextInt();
scanner.nextLine(); // <--- Limpieza del buffer (Enter fantasma)
String nombre = scanner.nextLine(); // Ahora si funciona
```
