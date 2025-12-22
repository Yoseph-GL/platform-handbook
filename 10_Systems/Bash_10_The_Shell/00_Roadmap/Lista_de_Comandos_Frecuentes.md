# Cheat Sheet: Comandos Esenciales Bash

## Navegacion y Sistema
| Comando | Descripcion | Ejemplo Tipico |
|:---|:---|:---|
| **pwd** | Imprime directorio actual | `pwd` |
| **cd** | Cambiar directorio | `cd /var/log` (Ir), `cd ..` (Atras), `cd ~` (Home) |
| **ls** | Listar archivos | `ls -la` (Listado largo + ocultos) |
| **tree** | Arbol de directorios | `tree -L 2` (Solo 2 niveles de profundidad) |
| **man** | Manual del comando | `man grep` (Salir con `q`) |
| **clear** | Limpiar pantalla | `clear` o `Ctrl+L` |

## Archivos y Directorios
| Comando | Descripcion | Ejemplo Tipico |
|:---|:---|:---|
| **mkdir** | Crear carpeta | `mkdir -p proyecto/logs` (Crea padres si no existen) |
| **touch** | Crear archivo vacio | `touch notas.txt` |
| **cp** | Copiar | `cp archivo.txt copia.txt` o `cp -r carpeta/ destino/` |
| **mv** | Mover o Renombrar | `mv viejo.txt nuevo.txt` |
| **rm** | Borrar (CUIDADO) | `rm archivo.txt` o `rm -rf carpeta/` (Forzado recursivo) |
| **ln** | Crear enlace | `ln -s /ruta/real /ruta/symlink` |

## Visualizacion y Busqueda
| Comando | Descripcion | Ejemplo Tipico |
|:---|:---|:---|
| **cat** | Imprimir todo el archivo | `cat config.json` |
| **less** | Leer paginado | `less archivo_largo.log` (Navegar con flechas) |
| **tail** | Ver final del archivo | `tail -f error.log` (Ver en tiempo real) |
| **head** | Ver inicio del archivo | `head -n 5 archivo.csv` |
| **grep** | Buscar texto | `grep "error" app.log` o `grep -r "config" .` |
| **find** | Buscar archivos | `find . -name "*.conf"` |

## Permisos y Admin
| Comando | Descripcion | Ejemplo Tipico |
|:---|:---|:---|
| **chmod** | Cambiar permisos | `chmod +x script.sh` (Hacer ejecutable) |
| **chown** | Cambiar dueño | `chown usuario:grupo archivo` |
| **sudo** | Ejecutar como root | `sudo apt update` |
| **ps** | Ver procesos | `ps aux | grep java` |
| **kill** | Terminar proceso | `kill -9 1234` (Matar PID 1234) |

## Networking
| Comando  | Descripcion        | Ejemplo Tipico                             |
| :------- | :----------------- | :----------------------------------------- |
| **ssh**  | Conectar remoto    | `ssh usuario@192.168.1.50`                 |
| **ping** | Verificar conexion | `ping 8.8.8.8`                             |
| **ip**   | Ver interfaces/IP  | `ip a`                                     |
| **curl** | Peticion HTTP      | `curl -I https://google.com` (Ver headers) |