# Iteracion Definida: For Loops

Usamos `for` cuando sabemos **cuantas veces** queremos repetir algo.

## 1. El Bucle For Clasico (Estilo C)
Ideal cuando necesitas el indice `i` (ej: para acceder a posiciones especificas o contar de 2 en 2).

**Sintaxis:** `for (inicio; condicion; paso)`

```java
// Contar del 0 al 4
for (int i = 0; i < 5; i++) {
    System.out.println("Indice: " + i);
}

// Contar hacia atras
for (int i = 10; i > 0; i--) {
    System.out.println("Cuenta regresiva: " + i);
}
```

## 2. El Bucle For-Each (Enhanced For)

Introducido en Java 5. Es mas limpio y seguro para recorrer Arrays o Colecciones completas. **Limitacion:** No tienes acceso al indice `i`. Solo obtienes el valor.
```java
String[] frutas = {"Manzana", "Pera", "Uva"};

// "Para cada fruta f en frutas"
for (String f : frutas) {
    System.out.println("Me gusta la " + f);
}
```

**Best Practice:** Usa siempre **For-Each** a menos que sea estrictamente necesario modificar el array original o usar el indice matematicamente.