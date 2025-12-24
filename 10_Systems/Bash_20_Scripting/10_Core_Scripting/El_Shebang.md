# El Shebang: #!

La primera linea de cualquier script profesional **DEBE** ser el Shebang. Es la instruccion que le dice al Kernel que interprete usar.

## Sintaxis
`#!` (Sharp-Bang -> Shebang) seguido de la ruta absoluta del interprete.

```
#!/bin/bash
echo "Hola Mundo"
```

Variantes Comunes

| **Shebang**           | **Interprete**         | **Uso**                                                                |
| --------------------- | ---------------------- | ---------------------------------------------------------------------- |
| `#!/bin/bash`         | Bash                   | Estandar en Linux.                                                     |
| `#!/bin/sh`           | Sh (Bourne)            | Maxima compatibilidad (POSIX), pero sin funciones avanzadas.           |
| `#!/usr/bin/env bash` | **Portabilidad (Pro)** | Busca bash en el PATH. Mejor si el script correra en Mac, Linux y BSD. |
| `#!/usr/bin/python3`  | Python                 | Para scripts en Python.                                                |

## ¿Que pasa si no lo pongo?

1. Si ejecutas con `bash script.sh`: Funciona (porque forzaste el interprete).
    
2. Si ejecutas con `./script.sh`: **Falla** o intenta usar la shell actual del usuario (arriesgado, podria ser Zsh o Fish y romper tu logica).
    

> **Regla de Oro:** Nunca dejes un archivo `.sh` sin Shebang, incluso si solo son 2 lineas.