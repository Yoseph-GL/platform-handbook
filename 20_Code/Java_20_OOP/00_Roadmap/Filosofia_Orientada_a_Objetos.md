# Filosofia: Programacion Orientada a Objetos (OOP)

La OOP no es solo sintaxis, es una forma de pensar. Dejas de pensar en "pasos a seguir" (procedural) y empiezas a pensar en **entidades que colaboran**.

## 1. Procedural vs OOP

### El Enfoque Procedural (C, Bash, Scripts simples)
El codigo es una lista de instrucciones y funciones que manipulan datos globales o pasados por parametro.
* **Problema:** Datos y logica estan separados. Si cambias la estructura de los datos, rompes todas las funciones.
* **Ejemplo:** `imprimirUsuario(nombre, edad)`.

### El Enfoque OOP (Java, C#, Python)
Agrupamos **Datos (Estado)** y **Logica (Comportamiento)** en una sola unidad llamada **Objeto**.
* **Ventaja:** El objeto es dueño de sus datos y responsable de su integridad.
* **Ejemplo:** `usuario.imprimir()`.

---

## 2. Los 4 Pilares Fundamentales
Toda la OOP se sostiene en estos conceptos. Debes memorizarlos y entenderlos.

### A. Encapsulamiento (Proteccion)
"Lo que pasa en el objeto, se queda en el objeto".
Ocultar los detalles internos y exponer solo una interfaz segura.
* *Ejemplo:* Un coche. Tu usas el volante y pedales (interfaz publica), pero no tocas la inyeccion de gasolina directamente (estado privado).

### B. Abstraccion (Simplificacion)
Enfocarse en las caracteristicas esenciales ignorando los detalles complejos.
* *Ejemplo:* Para manejar, solo necesitas saber que el coche "acelera". No necesitas saber termodinamica.

### C. Herencia (Reutilizacion)
Crear nuevas clases basadas en clases existentes. Relacion "Es un...".
* *Ejemplo:* Un `Deportivo` **es un** `Coche`. Hereda ruedas y motor, pero añade un turbo.

### D. Polimorfismo (Flexibilidad)
La capacidad de un objeto de tomar muchas formas.
* *Ejemplo:* Si tienes una lista de `Coche`, puedes tener dentro un `Ferrari` y un `Vocho`. Si llamas a `acelerar()`, el Ferrari rugira y el Vocho tosera, aunque la orden fue la misma.

---

## 3. Estado y Comportamiento

Al diseñar una clase, hazte dos preguntas:

1.  **¿Que sabe? (Atributos/Estado):** Nombre, edad, saldo, color. (Sustantivos).
2.  **¿Que hace? (Metodos/Comportamiento):** Caminar, calcularImpuestos, encender. (Verbos).