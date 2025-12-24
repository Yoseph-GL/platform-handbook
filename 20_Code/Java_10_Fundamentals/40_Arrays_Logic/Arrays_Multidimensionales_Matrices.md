# Arrays Multidimensionales (Matrices)

Básicamente, "Arrays de Arrays". Se usan para representar tablas, tableros de ajedrez o imágenes.

## 1. Sintaxis Básica (2D)

Piensa en filas `[ ]` y columnas `[ ]`.

```java
// Declarar una matriz de 3 filas x 3 columnas
int[][] matriz = new int[3][3];

// Inicialización Literal (Visualmente claro)
int[][] tablero = {
    {1, 0, 0}, // Fila 0
    {0, 1, 0}, // Fila 1
    {0, 0, 1}  // Fila 2
};
```

## 2. Acceso a Datos
```java
// matriz[FILA][COLUMNA]
int valor = tablero[1][1]; // Centro
tablero[0][0] = 9;         // Esquina superior izquierda
```

## 3. Iteración (Bucles Anidados)

Para recorrer una matriz completa, necesitas un bucle dentro de otro.
```java
// 'i' controla filas, 'j' controla columnas
for (int i = 0; i < tablero.length; i++) {
    for (int j = 0; j < tablero[i].length; j++) {
        System.out.print(tablero[i][j] + " ");
    }
    System.out.println(); // Salto de línea al terminar la fila
}
```

## 4. Arrays Irregulares (Jagged Arrays)

En Java, las filas no tienen que tener el mismo tamaño obligatoriamente.
```java
int[][] irregular = new int[3][]; // Solo defino filas

irregular[0] = new int[2]; // Fila 0 tiene 2 columnas
irregular[1] = new int[5]; // Fila 1 tiene 5 columnas
irregular[2] = new int[1]; // Fila 2 tiene 1 columna
```

