# Alterando el Flujo: Break y Continue

A veces necesitamos romper las reglas del bucle.

## 1. Break (Romper)
Termina el bucle mas cercano inmediatamente. Salta al codigo despues del `}`.

```java
// Buscar un numero
for (int i = 0; i < 100; i++) {
    if (i == 50) {
        System.out.println("Encontrado!");
        break; // Deja de contar, no llega a 99. Ahorra CPU.
    }
}
```

## 2. Continue (Saltar)

Salta la iteracion **actual** y pasa a la siguiente. Ignora el codigo que queda abajo en esa vuelta.
```java
// Imprimir solo pares
for (int i = 0; i < 10; i++) {
    if (i % 2 != 0) {
        continue; // Es impar, salta al siguiente 'i'
    }
    System.out.println("Par: " + i);
}
```

## 3. Labeled Break (Break con Etiquetas) - _Tecnica Avanzada_

Por defecto, `break` solo rompe el bucle interno. Si quieres romper dos bucles anidados (ej: salir de una matriz), usa etiquetas.
```java
busqueda: // Etiqueta
for (int i = 0; i < 5; i++) {
    for (int j = 0; j < 5; j++) {
        if (i == 2 && j == 2) {
            break busqueda; // Rompe AMBOS bucles
        }
    }
}
System.out.println("Salida completa.");
```
