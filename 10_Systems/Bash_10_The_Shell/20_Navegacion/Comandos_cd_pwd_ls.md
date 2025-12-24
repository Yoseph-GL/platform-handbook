# La Trinidad de la Navegacion: pwd, cd, ls

Estos tres comandos representan el 80% de lo que haras en la terminal.

## 1. pwd (Print Working Directory)
**¿Donde estoy?**
Imprime la ruta absoluta de tu ubicacion actual.

```bash
pwd
# Salida: /home/usuario/proyectos;
```
## 2. cd (Change Directory)

| **Comando**         | **Accion**                                              |
| ------------------- | ------------------------------------------------------- |
| `cd /ruta/destino`  | Ir a una ruta especifica.                               |
| `cd nombre_carpeta` | Entrar a una carpeta hija (relativo).                   |
| `cd ..`             | Subir un nivel (al padre).                              |
| `cd` (sin nada)     | Volver a **casa** (`~`).                                |
| `cd -`              | **Back:** Volver al directorio anterior (como Alt+Tab). |
## 3. ls (List)

**Vision.** Muestra el contenido del directorio.

### Banderas (Flags) Esenciales

Los comandos cambian su comportamiento con banderas (`-`).

| **Flag** | **Nombre**  | **Efecto**                                           |
| -------- | ----------- | ---------------------------------------------------- |
| `-l`     | **Long**    | Muestra permisos, dueño, tamaño y fecha.             |
| `-a`     | **All**     | Muestra archivos ocultos (los que empiezan con `.`). |
| `-h`     | **Human**   | Muestra tamaños en KB, MB, GB (usar con `-l`).       |
| `-r`     | **Reverse** | Invierte el orden de lista.                          |
| `-t`     | **Time**    | Ordena por fecha de modificacion (mas nuevo arriba). |
**El estandar de industria:**
ls -lah
(Listado largo + ocultos + tamaños legibles).

Para ver lo mas nuevo al final (ideal para logs):
ls -lrt