# Roadmap: Bash 101 - The Shell

## 1. Introduccion y Core
Objetivo: Entender donde estamos parados y configurar el entorno.
- [ ] [[Conceptos_Shell_vs_Terminal]] | Diferencia entre la ventana y el interprete.
- [ ] [[Prompt_y_Entorno]] | Entendiendo `usuario@host:~$`.
- [ ] [[Configuracion_Inicial]] | Atajos basicos y perfil.

## 2. Navegacion (Sobrevivencia)
Objetivo: Moverse por el sistema de archivos sin interfaz grafica.
- [ ] [[FHS_Sistema_de_Archivos]] | Estructura de Linux (`/bin`, `/etc`, `/var`).
- [ ] [[Rutas_Absolutas_vs_Relativas]] | La diferencia entre `/home/user` y `../user`.
- [ ] [[Comandos_cd_pwd_ls]] | La triada santa del movimiento.

## 3. Gestion de Archivos
Objetivo: CRUD (Create, Read, Update, Delete) de archivos y carpetas.
- [ ] [[Crear_Copiar_Mover]] | `touch`, `cp`, `mv`, `mkdir`.
- [ ] [[Borrado_Seguro]] | `rm` y como evitar desastres.
- [ ] [[Comodines_Wildcards]] | Uso de `*` y `?` para operaciones masivas.
- [ ] [[Enlaces_Simbolicos_ln]] | Accesos directos (`symlinks`) en Linux.

## 4. Visualizacion y Busqueda
Objetivo: Encontrar agujas en pajares (logs, configuraciones).
- [ ] [[Lectura_cat_less_head]] | Ver contenido sin abrir editores.
- [ ] [[Busqueda_Archivos_find]] | Encontrar archivos por nombre, fecha o tamaño.
- [ ] [[Busqueda_Texto_grep]] | Encontrar cadenas de texto DENTRO de archivos.

## 5. Permisos y Administracion
Objetivo: Seguridad basica y control de procesos.
- [ ] [[Usuario_Root_y_Sudo]] | Elevacion de privilegios.
- [ ] [[Permisos_rwx_y_chmod]] | Lectura, Escritura, Ejecucion.
- [ ] [[Propietarios_chown]] | Cambiar dueño y grupo.
- [ ] [[Procesos_ps_kill_top]] | Matar programas colgados.

## 6. Networking y Paquetes
Objetivo: Conectividad y gestion de software.
- [ ] [[Conexion_Remota_ssh]] | Administracion remota segura.
- [ ] [[Transferencia_curl_wget]] | Descargar archivos por terminal.
- [ ] [[Diagnostico_ping_ip]] | Troubleshooting de red basico.
- [ ] [[Gestores_Paquetes_apt_yum]] | Instalar y actualizar software.

## 7. Redirecciones y Pipes
Objetivo: Conectar comandos para crear flujos de trabajo.
- [ ] [[Streams_STDIN_STDOUT]] | Entender entrada y salida estandar.
- [ ] [[Operadores_Redireccion]] | Guardar outputs en archivos (`>`, `>>`).
- [ ] [[Tuberias_Pipes]] | Pasar el output de un comando a otro (`|`).
- [ ] [[Alias]] | Crear tus propios comandos cortos.