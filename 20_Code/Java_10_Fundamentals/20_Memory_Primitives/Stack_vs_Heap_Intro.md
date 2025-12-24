# Memoria: Stack vs Heap

Java divide la memoria RAM en dos áreas principales. Entender esto es vital para saber por qué `int` se comporta diferente a `String`.

## 1. Stack (La Pila) - "Orden y Rapidez"
Es una memoria pequeña, rápida y temporal.
* **¿Qué guarda?:**
    1.  Variables locales **primitivas** (`int`, `boolean`, `double`) dentro de un método.
    2.  Las **referencias** (los "controles remotos") que apuntan a objetos.
    3.  El flujo de ejecución de métodos (quién llamó a quién).
* **Ciclo de vida:** Cuando el método termina (`}`), todo lo que estaba en su bloque de Stack se borra inmediatamente.
* **Acceso:** LIFO (Last In, First Out).

## 2. Heap (El Montón) - "Caos y Objetos"
Es una memoria gigante y desordenada. 
* **¿Qué guarda?:** TODOS los **Objetos** reales (`new String()`, `new Scanner()`, arrays).
* **Ciclo de vida:** Los objetos viven aquí hasta que el **Garbage Collector** (el basurero automático de Java) decide que nadie los está usando y los borra.
* **Acceso:** Más lento que el Stack, se accede vía referencias.

## 3. El Diagrama Mental

```java
public void metodo() {
    int edad = 20;            // Vive en STACK
    Scanner sc = new Scanner(System.in); 
    // 'sc' (la variable) vive en STACK.
    // El objeto real Scanner vive en HEAP.
    // 'sc' es un cable que conecta Stack con Heap.
}
```

**Regla de Oro:** Los primitivos guardan **VALOR** (el número real). Los objetos guardan **DIRECCIÓN DE MEMORIA** (dónde encontrar el dato en el Heap).