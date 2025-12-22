# Permisos y chmod

Linux usa un sistema de permisos basado en 3 acciones y 3 grupos.
Al hacer `ls -l` veras algo como: `-rwxr-xr--`

## 1. Anatomia (rwx)

| Letra | Significado | Valor Octal | En Archivo | En Directorio |
|:---|:---|:---|:---|:---|
| **r** | Read (Lectura) | **4** | Ver contenido | Listar archivos (`ls`) |
| **w** | Write (Escritura) | **2** | Modificar/Borrar | Crear/Borrar archivos dentro |
| **x** | Execute (Ejecucion)| **1** | Correr script/binario | Entrar a la carpeta (`cd`) |
| **-** | Sin permiso | **0** | Denegado | Denegado |

## 2. Los 3 Niveles de Acceso (UGO)

La cadena `rwxr-xr--` se lee en grupos de 3:

1.  **User (u):** El dueño del archivo. (Primeros 3 caracteres).
2.  **Group (g):** El grupo dueño. (Siguientes 3 caracteres).
3.  **Others (o):** El resto del mundo. (Ultimos 3 caracteres).

## 3. El comando chmod (Change Mode)

Cambia los permisos. Existen dos metodos:

### Metodo Octal (Numerico - El mas rapido)
Sumas los valores (r=4, w=2, x=1).

* **7** (4+2+1) = rwx (Todo)
* **6** (4+2) = rw- (Leer y escribir)
* **5** (4+1) = r-x (Leer y ejecutar)
* **4** (4) = r-- (Solo lectura)

```
# Permisos estandar para archivos (Dueño: rw, Grupo: r, Otros: r)
chmod 644 config.txt

# Permisos estandar para scripts (Dueño: rwx, Grupo: rx, Otros: rx)
chmod 755 script.sh

# Permisos privados (Solo yo leo y escribo)
chmod 600 id_rsa
```

### Metodo Simbolico (Letras)

Mas facil de leer para humanos principiantes.

# Agregar ejecucion (+x) a todos (a)
chmod +x script.sh

# Quitar escritura (-w) a "otros" (o)
chmod o-w archivo_sensible.txt