# Gestion de Paquetes: apt y yum/dnf

En Linux no bajas `.exe` de paginas dudosas. Usas repositorios oficiales firmados criptograficamente.
Dependiendo de tu "Distro", el comando cambia.

## 1. Familia Debian / Ubuntu (`apt`)

```
# 1. Actualizar la lista de repositorios (Hacer siempre primero)
sudo apt update

# 2. Actualizar los programas instalados
sudo apt upgrade -y

# 3. Instalar un paquete
sudo apt install git nginx htop

# 4. Buscar un paquete
apt search python3

# 5. Borrar un paquete
sudo apt remove nginx
```

## 2. Familia RedHat / CentOS / Fedora (`yum` o `dnf`)

`dnf` es la version moderna de `yum`. Funcionan casi igual.
# Actualizar sistema
sudo dnf update

# Instalar
sudo dnf install git

# Buscar
dnf search docker

## 3. Limpieza

Los paquetes descargados ocupan espacio.
# Ubuntu/Debian
sudo apt autoremove  # Borra dependencias huerfanas
sudo apt clean       # Borra cache de instaladores