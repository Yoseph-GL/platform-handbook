# Bash 10: Hoja de Referencia Rapida (Cheatsheet)

## 1. Navegacion
| Comando | Descripcion |
|:---|:---|
| `pwd` | Muestra ruta actual. |
| `cd /ruta` | Ir a ruta absoluta. |
| `cd ..` | Subir un nivel. |
| `cd ~` | Ir a Home. |
| `cd -` | Volver al directorio anterior. |
| `ls -lah` | Listar todo + ocultos + tamaños legibles. |
| `tree -L 2` | Ver arbol de carpetas (2 niveles). |

## 2. Archivos y Directorios
| Comando | Descripcion |
|:---|:---|
| `mkdir -p a/b` | Crear carpeta (y sus padres). |
| `touch file` | Crear archivo vacio. |
| `cp -r dir1 dir2` | Copiar carpeta recursivamente. |
| `mv old new` | Renombrar o mover. |
| `rm file` | Borrar archivo. |
| `rm -rf dir` | **PELIGRO:** Borrar carpeta forzado. |
| `ln -s real link` | Crear enlace simbolico. |

## 3. Visualizacion y Busqueda
| Comando | Descripcion |
|:---|:---|
| `cat file` | Ver archivo completo. |
| `less file` | Ver archivo paginado (salir con `q`). |
| `head -n 5` | Ver primeras 5 lineas. |
| `tail -f log` | Ver log en tiempo real. |
| `grep "txt" file` | Buscar texto dentro de archivo. |
| `find . -name "*"` | Buscar archivo por nombre. |

## 4. Permisos
| Comando | Descripcion |
|:---|:---|
| `chmod +x script` | Hacer ejecutable. |
| `chmod 755 dir` | Permisos estandar directorios. |
| `chmod 644 file` | Permisos estandar archivos. |
| `chown user:group` | Cambiar dueño. |
| `sudo cmd` | Ejecutar como root. |

## 5. Sistema y Procesos
| Comando | Descripcion |
|:---|:---|
| `ps aux` | Ver todos los procesos. |
| `top` / `htop` | Monitor de recursos en vivo. |
| `kill PID` | Terminar proceso suave. |
| `kill -9 PID` | Matar proceso forzado. |
| `df -h` | Ver espacio en disco. |
| `free -h` | Ver memoria RAM. |

## 6. Redes
| Comando | Descripcion |
|:---|:---|
| `ip a` | Ver mis IPs. |
| `ping host` | Probar conectividad. |
| `curl -I url` | Ver headers HTTP. |
| `ssh user@host` | Conectar remoto. |
| `wget url` | Descargar archivo. |

## 7. Atajos de Teclado (Shortcuts)
| Tecla      | Accion                         |
| :--------- | :----------------------------- |
| `TAB`      | Autocompletar (USALO SIEMPRE). |
| `Ctrl + C` | Cancelar comando.              |
| `Ctrl + L` | Limpiar pantalla.              |
| `Ctrl + R` | Buscar en historial.           |
| `Ctrl + A` | Ir al inicio de linea.         |
| `Ctrl + E` | Ir al final de linea.          |