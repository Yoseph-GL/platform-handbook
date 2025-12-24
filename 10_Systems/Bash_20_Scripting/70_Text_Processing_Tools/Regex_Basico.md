# Expresiones Regulares (Regex)

Una Regex es un patron para encontrar texto. NO confundir con los Wildcards de Bash (`*.jpg`).

## 1. Anclas (Posicion)
* `^` : Inicio de linea.
* `$` : Final de linea.

```
grep "^Error" log.txt  # Lineas que EMPIEZAN con Error
grep "fin$" log.txt    # Lineas que TERMINAN con fin
```

## 2. Clases de Caracteres

- `.` : Cualquier caracter (excepto nueva linea).
    
- `[abc]` : Cualquiera de esos tres (a, b o c).
    
- `[0-9]` : Cualquier digito.
    
- `[A-Z]` : Cualquier mayuscula.
- # Buscar fechas formato 2023, 2024...
grep "202[0-9]" archivo.txt

## 3. Cuantificadores (Cantidad)

- `*` : 0 o mas veces.
    
- `+` : 1 o mas veces (Requiere `grep -E`).
    
- `?` : 0 o 1 vez (Opcional).
# Buscar http o https
grep -E "https?" urls.txt

## Resumen Visual

|Simbolo|Regex (grep/sed/awk)|Wildcard (ls/cp/mv)|
|---|---|---|
|`*`|Repite el anterior|Cualquier texto|
|`.`|Cualquier caracter|Un punto literal|
|`?`|Opcional|Un caracter cualquiera|
