# Recursividad Básica

La recursividad ocurre cuando un método **se llama a sí mismo**. Es una alternativa elegante a los bucles `while/for` para ciertos algoritmos.

## 1. Estructura de un Método Recursivo
Todo método recursivo DEBE tener dos partes o creará un bucle infinito (`StackOverflowError`).

1.  **Caso Base (Base Case):** La condición para DETENERSE.
2.  **Llamada Recursiva:** La llamada a sí mismo con un problema más pequeño.

## 2. Ejemplo Clásico: Factorial
Factorial de 5 (`5!`) es `5 * 4 * 3 * 2 * 1`.
Matemáticamente: `5! = 5 * 4!`

```java
public static int factorial(int n) {
    // 1. Caso Base: Factorial de 1 es 1. ¡FRENAMOS AQUI!
    if (n == 1) {
        return 1;
    }
    
    // 2. Llamada Recursiva
    return n * factorial(n - 1);
}
```

## 3. Análisis de Memoria (Stack)

Si llamas a `factorial(3)`:

1. `factorial(3)` entra al Stack. Pausa y llama a...
    
2. `factorial(2)` entra al Stack. Pausa y llama a...
    
3. `factorial(1)` entra al Stack. **Retorna 1** y sale.
    
4. `factorial(2)` recibe el 1, calcula `2 * 1`, retorna 2 y sale.
    
5. `factorial(3)` recibe el 2, calcula `3 * 2`, retorna 6 y sale.
    

## 4. Riesgos

La recursividad consume mucha memoria **Stack**.

- Si haces `factorial(100000)`, llenarás la pila y el programa crasheará (`StackOverflowError`).
    
- Para iteraciones profundas, usa bucles normales.