# Iteracion Indefinida: While y Do-While

Usamos estos bucles cuando **NO** sabemos cuantas veces vamos a iterar (ej: "leer hasta que el usuario escriba salir").

## 1. While (Mientras)
Evalua la condicion **ANTES** de ejecutar. Puede que nunca se ejecute.

```java
int tanque = 10;

while (tanque > 0) {
    System.out.println("Avanzando... Gasolina: " + tanque);
    tanque--; // Importante: modificar la condicion o sera infinito
}
System.out.println("Auto detenido.");
```

## 2. Do-While (Hacer... Mientras)

Evalua la condicion **AL FINAL**. **Garantia:** Se ejecuta **al menos una vez**, incluso si la condicion es falsa desde el inicio.
```java
Scanner sc = new Scanner(System.in);
int opcion;

do {
    System.out.println("1. Jugar");
    System.out.println("2. Salir");
    opcion = sc.nextInt();
} while (opcion != 2);

System.out.println("Adios!");
```

### Bucle Infinito (Daemons)

Comun en servidores o juegos que corren por siempre.
```java
while (true) {
    // Logica del servidor...
    // Necesita un 'break' interno para salir.
}
```
