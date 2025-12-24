# Métodos: Definición y Estructura

Un método es un bloque de código con nombre que realiza una tarea específica. En otros lenguajes se llaman "funciones", pero en Java, como viven dentro de clases, son "métodos".

## 1. Anatomía de un Método

```java
//   [1]     [2]    [3]      [4]           [5]
public static int sumar(int a, int b) {
    // [6] Cuerpo
    int resultado = a + b;
    return resultado; // [7]
}
```

- **Modificadores (`public static`):**
    
    - `public`: Visible desde cualquier lado.
        
    - `static`: No necesita un objeto para ejecutarse (Vital para este módulo de Fundamentals).
        
- **Tipo de Retorno (`int`):** Qué dato devuelve. Si no devuelve nada, usa **`void`**.
    
- **Nombre (`sumar`):** Verbo en infinitivo, camelCase.
    
- **Parámetros (`int a, int b`):** Inputs necesarios. Pueden ser cero o muchos.
    
- **Firma (Signature):** `nombre + tipos de parametros`. Es lo que identifica al método.
    
- **Cuerpo:** La lógica entre `{ }`.
    
- **Return:** Finaliza el método y entrega el valor.

## 2. Tipos de Retorno

### A. Con Retorno (Funciones Matemáticas)

Debes capturar el valor en una variable o usarlo directamente.
```java
public static double calcularArea(double radio) {
    return 3.14 * radio * radio;
}

// Uso:
double area = calcularArea(5.0);
```

### B. Sin Retorno (`void`)

Realizan una acción (imprimir, guardar, enviar email) y terminan.
```java
public static void saludar(String nombre) {
    System.out.println("Hola " + nombre);
    // No hay 'return' de valor, pero puedes usar 'return;' para salir antes.
}
```

## 3. Llamada a Métodos

Como estamos en `static` (mismo contexto que el main), los llamamos directo por su nombre.
```java
public static void main(String[] args) {
    saludar("Ana");      // Llamada a void
    int x = sumar(5, 5); // Llamada con retorno
}
```

