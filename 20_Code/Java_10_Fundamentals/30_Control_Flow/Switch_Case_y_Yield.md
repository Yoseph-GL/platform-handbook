# Switch: Clasico vs Moderno (Java 14+)

Java evoluciono. El `switch` antiguo era propenso a errores. El nuevo es una joya.

## 1. El Switch Clasico (Old School)
Requiere `break` en cada caso. Si lo olvidas, ejecuta todos los casos siguientes (Fall-through).

```java
int dia = 2;

switch (dia) {
    case 1:
        System.out.println("Lunes");
        break; // OBLIGATORIO
    case 2:
        System.out.println("Martes");
        break;
    default:
        System.out.println("Dia invalido");
}
```

## 2. El Switch Moderno (Arrow Syntax `->`)

Introducido en Java 14.

- No necesita `break`.
    
- Puede retornar valores directamente.
    
- Soporta multiples etiquetas en una linea.
 ```java
int dia = 2;

// Ejemplo: Usando switch como expresion (retorna valor)
String nombreDia = switch (dia) {
    case 1 -> "Lunes";
    case 2 -> "Martes";
    case 6, 7 -> "Fin de Semana"; // Multiples casos
    default -> "Dia Invalido";
};

System.out.println(nombreDia);
```

### Keyword `yield`

Si el bloque moderno necesita mas logica, usas `yield` para retornar el valor (es como un `return` pero solo para el switch).
```java
String tipo = switch (dia) {
    case 1 -> {
        System.out.println("Inicio de semana...");
        yield "Laboral"; // Retorna "Laboral"
    }
    default -> "Otro";
};
```
