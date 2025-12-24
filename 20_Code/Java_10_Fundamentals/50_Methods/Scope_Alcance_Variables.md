# Scope (Alcance) de Variables

El "Scope" define dónde una variable existe y dónde muere. Entender esto evita errores de "Variable not found".

## 1. Block Scope (Alcance de Bloque)
Cualquier variable declarada dentro de llaves `{ }` **SOLO** existe dentro de esas llaves.

```java
public static void metodo() {
    int x = 10; // Vive en todo el metodo
    
    if (x > 5) {
        int y = 20; // Solo vive en este IF
        System.out.println(x + y); // OK
    }
    
    // System.out.println(y); // ERROR: 'y' murio al cerrar el IF
    ```

## 2. Variables Locales vs Parámetros

Los parámetros de un método también son variables locales. Mueren cuando el método termina.
```java
public static void duplicar(int numero) {
    numero = numero * 2;
    // 'numero' muere aqui. No afecta a quien lo llamo (Paso por Valor).
}
```

## 3. Shadowing (Sombreado) - _Mala Práctica_

Ocurre cuando una variable interna tiene el mismo nombre que una externa. La interna "hace sombra" (oculta) a la externa.
```java
static int contador = 100; // Variable global (de clase)

public static void main(String[] args) {
    int contador = 50; // Variable local
    
    System.out.println(contador); // Imprime 50 (La local gana)
    
    // Si quieres la global, debes ser explicito (veremos esto en OOP)
    // System.out.println(Clase.contador); 
}
```

