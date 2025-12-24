# Strings: The String Pool & Immutability

Los `String` en Java son especiales. No son primitivos, pero tienen trucos de memoria para ahorrar RAM.

## 1. Inmutabilidad
Un objeto `String` **NUNCA CAMBIA**. Una vez creado en memoria, es eterno.

```java
String texto = "Hola";
texto = texto + " Mundo"; 

// ¿Cambio "Hola"? NO.
// 1. Se creó "Hola".
// 2. Se creó " Mundo".
// 3. Se creó "Hola Mundo".
// 4. La variable 'texto' ahora apunta al nuevo. El viejo "Hola" quedó basura.
```

## 2. String Pool (La Piscina)

Java guarda los textos literales (`"texto"`) en un área especial del Heap para reutilizarlos.
```java
String a = "Hola";
String b = "Hola";

// Como son idénticos, Java hace que 'a' y 'b' apunten AL MISMO lugar.
// Ahorra memoria.

System.out.println(a == b); // true (Misma dirección de memoria)
```

## 3. El Peligro del new String()

Si usas new, fuerzas a Java a crear un duplicado fuera del Pool. MALA PRÁCTICA.

```java
String c = new String("Hola");
System.out.println(a == c); // false (Distinta dirección)
```

Conclusión Crítica: NUNCA compares Strings con ==. Usa SIEMPRE texto.equals("Hola").