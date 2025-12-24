# Diferencias: JDK vs JRE vs JVM

Esta es la pregunta de entrevista #1 para Juniors. No puedes programar en Java sin entender esto.

## El Diagrama Mental

Imagina una matrioshka (muñecas rusas):
1. **JDK** (La mas grande, para desarrolladores).
2. Contiene al **JRE** (Para usuarios).
3. Contiene a la **JVM** (El cerebro).

---

## 1. JVM (Java Virtual Machine)
**"El Traductor"**

Es el motor que ejecuta el codigo. Tu escribes codigo Java (`.java`), el compilador lo convierte en **Bytecode** (`.class`), y la JVM interpreta ese Bytecode para el sistema operativo especifico (Windows, Linux, Mac).

* **Funcion:** Carga codigo, verifica seguridad y gestiona memoria (Garbage Collection).
* **Lema:** "Write Once, Run Anywhere".

## 2. JRE (Java Runtime Environment)
**"El Entorno de Ejecucion"**

Es lo que necesita un usuario normal para correr Minecraft o cualquier app Java.

* **Formula:** `JRE = JVM + Librerias del Sistema (rt.jar, java.util.*)`
* **Nota:** No incluye compilador (`javac`). Solo sirve para **correr** programas, no para crearlos.

## 3. JDK (Java Development Kit)
**"El Kit de Desarrollo"**

Es lo que instalas tu como ingeniero.

* **Formula:** `JDK = JRE + Herramientas de Desarrollo (javac, jdb, javadoc)`
* **Herramientas Clave:**
    * `javac`: El compilador.
    * `jar`: Para empaquetar ejecutables.
    * `javadoc`: Para generar documentacion.

---

## Resumen de Uso

| Rol                 | ¿Que instala?            | ¿Por que?                                                            |
| :------------------ | :----------------------- | :------------------------------------------------------------------- |
| **Gamer / Usuario** | **JRE** (o JVM embebida) | Solo necesita ejecutar la app.                                       |
| **Desarrollador**   | **JDK**                  | Necesita compilar y debuggear.                                       |
| **Servidor (Prod)** | **JRE** (Idealmente)     | Por seguridad y espacio, en produccion solo se corre, no se compila. |