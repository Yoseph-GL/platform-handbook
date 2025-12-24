# Paso de Parámetros: ¿Valor o Referencia?

Esta es la pregunta trampa de las entrevistas.
**VERDAD ABSOLUTA:** Java **SIEMPRE** pasa parámetros **POR VALOR (Copia)**.

## 1. Con Primitivos (Intuitivo)
Se copia el número. El original no se toca.

```java
void cambiar(int x) {
    x = 99; // Solo cambia la COPIA local
}

int numero = 10;
cambiar(numero);
System.out.println(numero); // Imprime 10 (Intacto)
```

## 2. Con Objetos (La Confusión)

Se copia la REFERENCIA (el control remoto), no el objeto entero. Pero como tienes una copia del control remoto... ¡puedes modificar el televisor original!
```java
void cambiarArray(int[] arr) {
    // arr es una COPIA de la referencia.
    // Pero ambas apuntan al MISMO array en el Heap.
    arr[0] = 99; 
}

int[] misNumeros = {1, 2, 3};
cambiarArray(misNumeros);
System.out.println(misNumeros[0]); // Imprime 99 (MODIFICADO)
```

¿Por qué decimos que es "Por Valor"?

Si intentas cambiar la referencia misma (hacer que apunte a otro lado), no afecta al original.
```java
void cambiarObjeto(String s) {
    s = "Nuevo Texto"; // Esto crea un nuevo String local.
    // La variable 's' original de afuera sigue apuntando al viejo.
}
```
