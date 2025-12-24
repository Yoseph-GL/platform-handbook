# Rutas: Absolutas vs Relativas
Para moverte en el arbol de directorios, tienes dos formas de dar direcciones al sistema. 
## 1. Ruta Absoluta (GPS) Es la direccion completa desde la raiz `/`. *

**Caracteristica:** Siempre empieza con `/`. 

**Ventaja**: Funciona sin importar donde estes parado. * 

**Desventaja:** Es larga de escribir.

**Ejemplo:** ```bash cd /var/log/nginx/```

## 2. Ruta Relativa (Indicaciones)

Es la direccion basada en tu posicion actual.

- **Caracteristica:** NO empieza con `/`.
    
- **Ventaja:** Rapida y corta.
    
- **Desventaja:** Si te mueves, la referencia cambia.
    

**Simbolos de Navegacion:**

- `.` (Punto) = Directorio **Actual**.
    
- `..` (Doble punto) = Directorio **Padre** (Arriba).
    
- `~` (Tilde) = Directorio **Home** del usuario.
    

### Ejemplos Comparativos

Supongamos que estas en `/home/usuario`. Quieres ir a `/var/log`.

Via Absoluta:
cd /var/log

Via Relativa:
cd ../../var/log

**Explicacion: Sube a /home (..), sube a / (..), baja a var, baja a log.

> **Regla de Oro:**
> 
> - Usa **Absolutas** en scripts y tareas programadas (cron) para evitar errores.
>     
> - Usa **Relativas** cuando exploras interactivamente para velocidad.
>