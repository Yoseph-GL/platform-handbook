# La Clase java.util.Arrays

Java incluye una clase de utilidad estática para manipular arrays sin escribir bucles manualmente. **Úsala siempre.**

**Importación:** `import java.util.Arrays;`

## 1. Imprimir Bonito (`toString`)
Convierte el array a un String legible formato `[a, b, c]`.

```java
int[] numeros = {10, 20, 30};
System.out.println(Arrays.toString(numeros));
// Salida: [10, 20, 30]

// Para Matrices (2D), usa deepToString
int[][] matriz = {{1, 2}, {3, 4}};
System.out.println(Arrays.deepToString(matriz));
// Salida: [[1, 2], [3, 4]]
```

## 2. Ordenar (`sort`)

Ordena el array original (Modifica los datos). Algoritmo: Dual-Pivot Quicksort.
```java
int[] desorden = {5, 1, 9, 3};
Arrays.sort(desorden);

System.out.println(Arrays.toString(desorden)); 
// [1, 3, 5, 9]
```

## 3. Búsqueda Binaria (binarySearch)

Busca un elemento y devuelve su índice. Requisito: El array DEBE estar ordenado previamente con sort().
```java
int[] ordenados = {10, 20, 30, 40};
int index = Arrays.binarySearch(ordenados, 30);

System.out.println(index); // 2
// Si devuelve negativo, significa que NO lo encontró.
```

## 4. Copiar (`copyOf`)

Para crear una copia real en otra dirección de memoria (Stack vs Heap) o para redimensionar.
```java
int[] original = {1, 2, 3};

// Copia exacta
int[] copia = Arrays.copyOf(original, original.length);

// Copia mas grande (Padding con ceros)
int[] grande = Arrays.copyOf(original, 5); 
// [1, 2, 3, 0, 0]
```

## 5. Comparar (`equals`)

Recuerda que `arr1 == arr2` compara referencias de memoria. Para comparar contenido:
```java
int[] a = {1, 2};
int[] b = {1, 2};

System.out.println(a == b); // false (Distinta memoria)
System.out.println(Arrays.equals(a, b)); // true (Mismo contenido)
```

