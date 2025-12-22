# Entrecomillado (Quoting Rules)

En Bash, los espacios son separadores de argumentos. Las comillas son el pegamento. Usar las incorrectas rompera tu script.

## 1. Sin Comillas (Peligro)
Bash interpreta espacios y caracteres especiales (`$`, `*`, `!`).

```
archivo=foto vacaciones.jpg
rm $archivo
# ERROR: Bash intenta borrar "foto" y luego "vacaciones.jpg".
```

## 2. Comillas Dobles `"` (Soft Quotes)

**Interpolacion.** Protege los espacios, pero **PERMITE** variables y comandos.
nombre="Mundo"
echo "Hola $nombre"
# Salida: Hola Mundo

## 3. Comillas Simples `'` (Hard Quotes)

**Literalidad Absoluta.** Nada dentro se interpreta. Lo que ves es lo que hay.
nombre="Mundo"
echo 'Hola $nombre'
# Salida: Hola $nombre

## Tabla de Resumen

| Caracter       | Sin Comillas     | Comillas Dobles `"` | Comillas Simples `'` |
| -------------- | ---------------- | ------------------- | -------------------- |
| Espacio        | Separador        | Literal             | Literal              |
| `$` (Variable) | Expande          | Expande             | Literal (Texto $)    |
| `*` (Glob)     | Expande archivos | Literal             | Literal              |
| `\` (Escape)   | Escapa sig.      | Escapa `$` `"` `\`  | Literal              |
**Best Practice:** Encierra **SIEMPRE** tus variables en comillas dobles, a menos que tengas una razon especifica para no hacerlo. _Bien:_ `cp "$origen" "$destino"`