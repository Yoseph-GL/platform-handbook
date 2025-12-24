# Type Casting (Conversión de Tipos)

A veces necesitas que un `double` quepa en un `int`. Java es estricto con esto para evitar pérdida de datos.

## 1. Casting Implícito (Widening)
De pequeño a grande. Es automático y seguro.
`byte` -> `short` -> `int` -> `long` -> `float` -> `double`

```java
int myInt = 9;
double myDouble = myInt; // Automático: 9.0
```

## 2. Casting Explícito (Narrowing)

De grande a pequeño. **PELIGROSO**. Debes firmar un contrato diciendo "Yo me hago cargo si se pierden datos". Se hace con paréntesis `(tipo)`.
```java
double precio = 9.99;
int precioEntero = (int) precio; 

System.out.println(precioEntero); // 9
// ¡Se perdieron los decimales! No redondea, TRUNCA.
```

## 3. El Desbordamiento (Overflow)

¿Qué pasa si metes un número gigante en una caja pequeña? Da la vuelta y se vuelve negativo.
```java
int grande = 130;
byte pequeño = (byte) grande; // El máximo de byte es 127

System.out.println(pequeño); // -126 (Comportamiento cíclico impredecible)
```