# Alias: Atajos Personalizados

Un alias es un nombre corto para un comando largo. Son vitales para la productividad diaria.

## Creacion Temporal (Dura solo esta sesion)
```
alias c='clear'
alias puertos='netstat -tulanp'
```

## Gestion

### Listar alias

Sin argumentos, muestra lo que tienes definido.
alias

Borrar alias
unalias c

## Escapar un Alias

Si creaste un alias para `cp` pero esta vez quieres usar el `cp` original real (sin tus banderas modificadas): Pon una barra invertida antes.
\cp archivo1 archivo2

## Alias Recomendados (Top Tier)

Añade esto a tu `.bashrc`:
# Navegacion
alias ..='cd ..'
alias ...='cd ../..'

# Grep con colores (ayuda visual)
alias grep='grep --color=auto'

# Git (si lo usas)
alias gs='git status'
alias ga='git add'
alias gc='git commit -m'

# Ip rapida
alias miip='curl ifconfig.me'