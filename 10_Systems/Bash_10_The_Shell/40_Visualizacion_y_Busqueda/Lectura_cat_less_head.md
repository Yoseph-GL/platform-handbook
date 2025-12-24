# Lectura de Archivos: cat, less, head, tail

Como SysAdmin, pasaras la mitad de tu vida leyendo logs y archivos de configuracion. No uses editores de texto (`nano`/`vim`) solo para leer; es lento y peligroso (podrias modificar algo por error).

## 1. Visualizacion Completa: cat

**Uso:** Archivos pequeños (configuraciones cortas).
`cat` (Concatenate) imprime todo el contenido de golpe en la pantalla.

```
cat /etc/hosts
```

- **Truco:** `cat -n archivo` muestra los numeros de linea.
    
- **Inverso:** `tac archivo` imprime el archivo al reves (la ultima linea primero).

## 2. Visualizacion Paginada: less

**Uso:** Archivos grandes/gigantes. `less` carga el archivo poco a poco. No satura la memoria RAM.

less /var/log/syslog

**Navegacion dentro de less:**

- `Espacio`: Avanzar una pagina.
    
- `b`: Retroceder una pagina (Back).
    
- `/texto`: Buscar "texto" hacia abajo (como Ctrl+F).
    
- `n`: Ir a la siguiente coincidencia de la busqueda.
    
- `q`: Salir (Quit).
    

## 3. Visualizacion Parcial: head y tail

Solo quieres ver el principio o el final.

### head (Cabecera)

Ver las primeras lineas (util para ver la estructura de un CSV).

head -n 5 archivo.csv # Muestra solo las primeras 5 lineas

### tail (Cola) - CRITICO

Ver las ultimas lineas. Es el comando mas usado para **Monitoreo**.

1. **Uso estatico:** Ver el error mas reciente.

tail -n 20 error.log

Uso en tiempo real (Follow):

tail -f access.log

- La consola se queda "colgada" esperando nuevas lineas.
    
- Veras las visitas/errores **mientras ocurren**.
    
- Salir con `Ctrl + C`.