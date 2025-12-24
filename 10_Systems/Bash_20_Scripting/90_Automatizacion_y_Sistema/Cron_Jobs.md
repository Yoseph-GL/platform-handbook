# Programacion de Tareas: Cron Jobs

Cron es el reloj despertador de Linux. Permite ejecutar scripts en horarios específicos (cada minuto, cada lunes, a las 3 AM, etc.).

## 1. La Sintaxis Sagrada (Las 5 Estrellas)

El formato es: `minuto hora dia_mes mes dia_semana comando`

| Campo | Rango | Ejemplo |
|:---|:---|:---|
| Minuto | 0-59 | `30` (A y media) |
| Hora | 0-23 | `14` (2 PM) |
| Día Mes | 1-31 | `15` (El quincena) |
| Mes | 1-12 | `1` (Enero) |
| Día Semana | 0-6 (0=Domingo) | `5` (Viernes) |

### Ejemplos Comunes
```
# Ejecutar todos los dias a las 3:00 AM
0 3 * * * /home/user/backup.sh

# Ejecutar cada 15 minutos
*/15 * * * * /home/user/check_ping.sh

# Ejecutar solo los Lunes a las 8:00 AM
0 8 * * 1 /home/user/reporte_semanal.sh
```

## 2. Gestión de Cron

- **Editar:** `crontab -e` (Abre el editor para tu usuario).
    
- **Listar:** `crontab -l` (Muestra lo que tienes programado).
    
- **Borrar todo:** `crontab -r` (Cuidado con esto).
    

## 3. Atajos (@shortcuts)

Cron tiene alias para no pensar en asteriscos.

| Atajo     | Equivalente                                           |
| --------- | ----------------------------------------------------- |
| `@reboot` | **Vital:** Se ejecuta una sola vez al encender la PC. |
| `@daily`  | `0 0 * * *` (A media noche).                          |
| `@hourly` | `0 * * * *` (Cada hora en punto).                     |

## 4. El error #1: Rutas y Entorno

Cron **NO** carga tu `.bashrc`. No conoce tus alias ni tus variables de entorno.

- **MAL:** `python script.py` (Cron no sabe donde está python).
    
- **BIEN:** `/usr/bin/python3 /home/juan/scripts/script.py` (Rutas absolutas siempre).
    

> **Tip:** Redirige siempre la salida para poder depurar, o Cron intentará enviarte un email local que nunca leerás. `0 3 * * * /script.sh >> /var/log/mi_cron.log 2>&1`