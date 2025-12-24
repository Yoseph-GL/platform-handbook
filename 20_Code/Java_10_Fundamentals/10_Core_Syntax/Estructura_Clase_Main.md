# Anatomia de un Programa Java

En Java, **TODO** debe vivir dentro de una clase. No existen funciones sueltas ni scripts globales.

## 1. La Estructura Minima
Para que un programa corra, necesita un "Punto de Entrada" (Entry Point).

```java
// 1. Definicion de la Clase
// El nombre del archivo DEBE ser Main.java
public class Main {

    // 2. El Metodo Main (Entry Point)
    // public: Visible para todos (la JVM necesita verlo).
    // static: Se ejecuta sin crear una instancia de la clase.
    // void: No retorna ningun valor al sistema operativo.
    // main: El nombre reservado que busca la JVM.
    // String[] args: Argumentos de linea de comandos.
    public static void main(String[] args) {
        
        // 3. Sentencias
        System.out.println("Hola Mundo desde Java");
    }
}
```

## 2. Reglas de Oro

1. **Case Sensitive:** `Main` no es lo mismo que `main`. Java distingue mayusculas.
    
2. **Nombre de Archivo:** Si la clase es `public class Usuario`, el archivo **DEBE** llamarse `Usuario.java`.
    
3. **Punto y Coma:** Todas las sentencias terminan con `;`. Si lo olvidas, no compila.
    
4. **Bloques:** El codigo se agrupa con llaves `{ }`.


## 3. Comentarios
```java
// Comentario de una sola linea

/*
   Comentario de bloque
   o multilinea
*/

/**
 * Javadoc: Comentario especial para documentacion.
 * Se usa sobre clases y metodos.
 */
```

