# Roadmap: Java 02 - Object Oriented Programming

Aqui dejamos de escribir "scripts" lineales y empezamos a diseñar **Sistemas**. Entenderas como modelar el mundo real en codigo.

## 1. Class Design (El Plano)
Objetivo: Crear moldes para objetos robustos.
- [ ] [[Clases_vs_Objetos]] | Instanciacion y el operador `new`.
- [ ] [[Constructores_y_Default]] | Inicializacion de objetos.
- [ ] [[Modificadores_Acceso_Public_Private]] | Proteger tus datos (Encapsulamiento I).
- [ ] [[Keyword_This]] | Diferenciar atributos de parametros.

## 2. Encapsulation & Beans
Objetivo: Proteger el estado interno del objeto.
- [ ] [[Getters_y_Setters]] | Acceso controlado.
- [ ] [[Invariantes_y_Validacion]] | Evitar objetos invalidos (ej: edad negativa).
- [ ] [[JavaBeans_Standard]] | Estandares de la industria para datos.

## 3. Static Members (Contexto de Clase)
Objetivo: Entender lo que NO pertenece al objeto.
- [ ] [[Variables_Estaticas]] | Memoria compartida entre instancias.
- [ ] [[Metodos_Estaticos_vs_Instancia]] | `static` vs metodos normales.
- [ ] [[Clase_Math_y_Constantes]] | `public static final`.

## 4. Inheritance & Polymorphism (Reutilizacion)
Objetivo: La base de la OOP. "Es un...".
- [ ] [[Herencia_Extends]] | Reutilizar codigo de clases padre.
- [ ] [[Keyword_Super]] | Acceder al padre.
- [ ] [[Sobreescritura_Overriding]] | Cambiar comportamiento heredado (`@Override`).
- [ ] [[Polimorfismo_de_Subtipos]] | Tratar al hijo como si fuera el padre.
- [ ] [[Clase_Object_ToString_Equals]] | Los metodos que todos tienen.

## 5. Abstraction (Contratos)
Objetivo: Definir QUE hace algo, sin decir COMO.
- [ ] [[Clases_Abstractas]] | Plantillas incompletas.
- [ ] [[Interfaces_y_Contratos]] | La pieza clave de la arquitectura limpia.
- [ ] [[Composicion_vs_Herencia]] | Por que heredar suele ser mala idea.

## 6. Exception Handling (Robustez)
Objetivo: Manejar errores sin crashear el programa.
- [ ] [[Try_Catch_Finally]] | Capturar errores.
- [ ] [[Jerarquia_Throwable]] | Error vs Exception.
- [ ] [[Checked_vs_Unchecked]] | Excepciones obligatorias vs runtime.