# Operadores: Matematicas y Logica

Herramientas para manipular datos.

## 1. Aritmetica Basica

```java
int a = 10;
int b = 3;

System.out.println(a + b); // 13 (Suma)
System.out.println(a - b); // 7  (Resta)
System.out.println(a * b); // 30 (Multiplicacion)
System.out.println(a / b); // 3  (Division ENTERA - trunca decimales)
System.out.println(a % b); // 1  (Modulo - el resto de la division)
```

## 2. Incremento y Decremento
```java
int x = 5;
x++; // x ahora es 6 (Post-incremento)
x--; // x vuelve a ser 5
x += 10; // x = x + 10 (Suma rapida)
```

## 3. Comparacion (Devuelven boolean)
```java
// a = 10, b = 3
boolean esMayor = a > b;  // true
boolean esIgual = a == b; // false (Cuidado: es doble igual)
boolean distinto = a != b;// true
```

## 4. Operadores Logicos (Tablas de Verdad)

Se usan para combinar condiciones.

| Operador | Nombre  | Descripcion                             |
| -------- | ------- | --------------------------------------- |
| `&&`     | **AND** | True si AMBOS son true.                 |
| `\|`     | **OR**  | True si AL MENOS UNO es true.           |
| `!`      | **NOT** | Invierte el valor (`!true` es `false`). |
```java
boolean tieneLicencia = true;
boolean tieneAuto = false;

if (tieneLicencia && tieneAuto) {
    System.out.println("Puede manejar"); // No se ejecuta
}
```

