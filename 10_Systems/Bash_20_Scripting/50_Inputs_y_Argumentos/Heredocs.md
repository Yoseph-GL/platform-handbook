# Heredocs (Here Documents)

Permiten pasar bloques de texto multilínea a un comando o crear archivos de texto plano desde el script. Es mas limpio que hacer 20 `echo` seguidos.

## 1. Crear Archivos de Configuracion
Sintaxis: `cat <<EOF > archivo.txt`

```
cat <<EOF > /etc/nginx/conf.d/miweb.conf
server {
    listen 80;
    server_name midominio.com;
    root /var/www/html;
}
EOF
```

- `EOF` es un delimitador (End Of File). Puedes usar cualquier palabra (ej: `FIN`, `LIMIT`).

## 2. Con Variables (Interpolacion)

```
Por defecto, las variables `$VAR` dentro del bloque se expanden.
port=8080
cat <<EOF > config.txt
El puerto es: $port
EOF
# Resultado: El puerto es: 8080
```

## 3. Sin Variables (Literal)

Si estas generando codigo (ej: otro script de bash o SQL) y no quieres que bash toque los `$`, pon el delimitador entre comillas simples `'EOF'`.
cat <<'EOF' > script.sh
echo "Mi variable home es $HOME"
EOF
# Resultado: echo "Mi variable home es $HOME" (Literal)