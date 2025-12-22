# Modos de Ejecucion: Fork vs Source

Entender esto distingue a un novato de un senior. Determina **donde** corren tus variables.

## 1. Ejecucion Estandar (Forking)
Comandos: `./script.sh` o `bash script.sh`

* **Comportamiento:** La shell actual crea una COPIA de si misma (Sub-shell).
* **Aislamiento:** El script corre en la copia. Al terminar, la copia se destruye.
* **Efecto:** Las variables creadas en el script **NO** afectan a tu terminal actual.

```
# script.sh contiene: export MI_VAR="Hola"
./script.sh
echo $MI_VAR
# Salida: (vacio) -> La variable murio con la sub-shell.
```

## 2. Ejecucion "Sourcing"

Comandos: `source script.sh` o `. script.sh` (Punto espacio archivo).

- **Comportamiento:** Lee el codigo y lo ejecuta en la **Shell Actual**.
    
- **Peligro:** Si el script tiene un `exit`, **CERRARA TU TERMINAL**.
    
- **Uso:** Cargar configuraciones, variables de entorno o activar entornos virtuales (como `venv` en Python).
# script.sh contiene: export MI_VAR="Hola"
source script.sh
echo $MI_VAR
# Salida: Hola -> La variable persiste.

## Resumen

| Metodo             | Crea Sub-shell | Persistencia de Variables | Uso Tipico              |
| ------------------ | -------------- | ------------------------- | ----------------------- |
| `./script.sh`      | SI             | No                        | Correr programas/tools. |
| `source script.sh` | NO             | Si                        | Cargar config/.bashrc.  |