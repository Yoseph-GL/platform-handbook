# Setup del Entorno: JDK & IDE

Java requiere un "Runtime" para funcionar. A diferencia de Python o JS, es tipado estatico y compilado, por lo que el setup es mas estricto.

## 1. Elegir el JDK (Java Development Kit)

Oracle Java ya no es la unica opcion (y tiene licencias complicadas). Usaremos distribuciones **OpenJDK** gratuitas y estables.

### Recomendacion: Eclipse Temurin (Adoptium) o Amazon Corretto
Son las versiones mas estables para produccion.

1.  **Version:** Descarga **Java 17 LTS** (Long Term Support) o **Java 21 LTS**. Evita las versiones impares (19, 23) para aprender, son experimentales.
2.  **Instalacion:**
    * **Windows:** Descarga el `.msi`. Asegurate de marcar la casilla *"Set JAVA_HOME variable"*.
    * **Mac/Linux:** Usa un gestor de versiones como `sdkman`.
        ```bash
        curl -s "[https://get.sdkman.io](https://get.sdkman.io)" | bash
        sdk install java 17.0.8-temurin
        ```

### Verificar Instalacion
Abre una terminal y ejecuta:
```
java -version
javac -version
```


