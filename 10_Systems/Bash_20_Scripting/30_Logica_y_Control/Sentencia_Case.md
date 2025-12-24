# Sentencia Case (Switch)

Cuando tienes muchos `if / elif / elif`, el codigo se vuelve sucio. Usa `case` para menus o procesar banderas.

## Sintaxis
* `case` inicia.
* `esac` termina.
* `)` cierra el patrón.
* `;;` es el "break" (termina la opción).

```
read -p "¿Que distro usas? " distro

case "$distro" in
    "Ubuntu" | "Debian")
        echo "Usas apt para instalar."
        ;;
    "CentOS" | "Fedora" | "RHEL")
        echo "Usas dnf/yum para instalar."
        ;;
    "Arch")
        echo "Usas pacman, btw."
        ;;
    *)
        echo "No conozco esa distro."
        ;;
esac
```

## Patron `*` (Default)

La opcion `*)` al final atrapa cualquier cosa que no haya coincidido arriba. Es el `default` de otros lenguajes.