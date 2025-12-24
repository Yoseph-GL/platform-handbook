# Toma de Decisiones: If, Else y Ternario

La estructura fundamental para bifurcar el codigo.

## 1. El Bloque If-Else Clasico

```java
int edad = 18;

if (edad >= 18) {
    System.out.println("Es mayor de edad");
    // Puedes tener multiples lineas aqui
} else if (edad >= 13) {
    System.out.println("Es adolescente");
} else {
    System.out.println("Es niño");
}
```

### El Peligro de las Llaves `{ }` Omitidas

Java permite omitir las llaves si solo hay una linea. **NUNCA LO HAGAS**.
```java
// MAL (Peligroso si agregas una linea despues)
if (error) System.out.println("Fallo");

// BIEN (Siempre usa llaves)
if (error) {
    System.out.println("Fallo");
}
```

## 2. El Operador Ternario `? :`

Es un `if-else` comprimido en una sola linea. Ideal para asignaciones simples. **Sintaxis:** `condicion ? valor_si_true : valor_si_false`
```java
int calificacion = 8;

// Version larga
String estado;
if (calificacion >= 6) {
    estado = "Aprobado";
} else {
    estado = "Reprobado";
}

// Version Pro (Ternario)
String estadoRapido = (calificacion >= 6) ? "Aprobado" : "Reprobado";
```

**Regla:** Usalo solo para asignaciones cortas. Si anidas ternarios (`a ? b : c ? d : e`), tu codigo se vuelve ilegible.