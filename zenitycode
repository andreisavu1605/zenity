#!/bin/bash

# Array con comandos y descripciones
comandos=(
    "ls - Listar directorios y archivos"
    "cd - Cambiar de directorio"
    "pwd - Mostrar el directorio actual"
    "mkdir - Crear un directorio"
    "rmdir - Eliminar un directorio"
    "touch - Crear un archivo vacío"
    "cp - Copiar archivos o directorios"
    "mv - Mover o renombrar archivos o directorios"
    "rm - Eliminar archivos o directorios"
    "chmod - Cambiar permisos de archivos o directorios"
    "chown - Cambiar propietario de archivos o directorios"
    "find - Buscar archivos o directorios"
    "grep - Buscar en el contenido de archivos"
    "cat - Concatenar y mostrar el contenido de archivos"
    "echo - Mostrar mensajes"
    "less - Ver el contenido de archivos página por página"
    "more - Ver el contenido de archivos página por página"
    "head - Mostrar las primeras líneas de un archivo"
    "tail - Mostrar las últimas líneas de un archivo"
    "nano - Editor de texto"
    "vim - Editor de texto avanzado"
    "apt-get - Gestor de paquetes de Debian y Ubuntu"
    "yum - Gestor de paquetes de Red Hat y CentOS"
    "dnf - Gestor de paquetes de Fedora"
    "ssh - Conexión a un servidor remoto"
    "scp - Copiar archivos entre hosts"
    "wget - Descargar archivos de la web"
    "curl - Herramienta para transferir datos"
    "tar - Trabajar con archivos tar"
    "gzip - Comprimir archivos"
    "gunzip - Descomprimir archivos gzip"
    "zip - Comprimir archivos en formato zip"
    "unzip - Descomprimir archivos zip"
    "ps - Mostrar procesos en ejecución"
    "top - Mostrar procesos en ejecución en tiempo real"
    "htop - Mostrar procesos en ejecución en tiempo real (más avanzado)"
    "kill - Terminar procesos"
    "killall - Terminar todos los procesos con el mismo nombre"
    "pkill - Terminar procesos basados en un patrón"
    "bg - Reanudar un trabajo suspendido en segundo plano"
    "fg - Reanudar un trabajo suspendido en primer plano"
    "jobs - Mostrar trabajos en segundo plano"
    "man - Mostrar el manual de un comando"
    "info - Mostrar información sobre comandos"
    "alias - Crear alias para comandos"
    "unalias - Eliminar alias de comandos"
    "df - Mostrar uso del disco"
    "du - Estimar uso del disco"
    "free - Mostrar uso de la memoria"
    "uname - Mostrar información del sistema"
    "hostname - Mostrar o establecer el nombre del host"
    "date - Mostrar o establecer la fecha y hora"
    "cal - Mostrar un calendario"
    "who - Mostrar quién está conectado"
    "whoami - Mostrar el nombre de usuario actual"
    "id - Mostrar identidad del usuario"
    "uptime - Mostrar el tiempo de actividad del sistema"
    "dmesg - Mostrar mensajes del kernel"
    "sysctl - Modificar parámetros del kernel"
    "lsblk - Mostrar información de dispositivos de bloques"
    "mount - Montar sistemas de archivos"
    "umount - Desmontar sistemas de archivos"
    "fdisk - Manipular tablas de particiones"
    "mkfs - Crear sistemas de archivos"
    "fsck - Verificar y reparar sistemas de archivos"
    "crontab - Gestionar trabajos programados"
    "at - Ejecutar comandos en un momento específico"
    "service - Gestionar servicios del sistema"
    "systemctl - Gestionar el sistema y servicios"
    "journalctl - Ver registros de systemd"
    "ufw - Configurar el firewall"
    "iptables - Configurar reglas de firewall"
    "ip - Mostrar o configurar interfaces de red"
    "ifconfig - Mostrar o configurar interfaces de red (obsoleto)"
    "ping - Comprobar conectividad de red"
    "traceroute - Rastrear la ruta a un host"
    "netstat - Mostrar conexiones de red"
    "ss - Mostrar sockets"
    "route - Mostrar o configurar la tabla de enrutamiento"
    "arp - Mostrar o manipular la caché ARP"
    "iwconfig - Configurar interfaces inalámbricas"
    "iwlist - Listar redes inalámbricas"
    "nmcli - Gestionar conexiones de red"
    "nmtui - Gestionar conexiones de red (interfaz de usuario)"
    "ftp - Transferir archivos"
    "sftp - Transferir archivos de forma segura"
    "rsync - Sincronizar archivos y directorios"
    "screen - Gestionar sesiones de terminal"
    "tmux - Gestionar sesiones de terminal (más avanzado)"
    "nohup - Ejecutar comandos sin colgarse"
    "history - Mostrar historial de comandos"
    "clear - Limpiar la pantalla del terminal"
    "reset - Resetear la pantalla del terminal"
    "bc - Calculadora de línea de comandos"
    "expr - Evaluar expresiones"
    "awk - Manipular y analizar texto"
    "sed - Editar flujos de texto"
    "cut - Eliminar secciones de cada línea de archivos"
    "paste - Unir líneas de archivos"
    "sort - Ordenar líneas de texto"
    "uniq - Reportar o eliminar líneas duplicadas"
    "wc - Contar líneas, palabras y caracteres"
    "tee - Leer de entrada estándar y escribir en la salida estándar y archivos"
    "diff - Comparar archivos línea por línea"
    "cmp - Comparar archivos byte a byte"
    "comm - Comparar archivos línea por línea"
    "ln - Crear enlaces físicos o simbólicos"
)

# Funciones para administrar usuarios y grupos
crear_usuario() {
    usuario=$(zenity --entry --title="Crear usuario" --text="Introduce el nombre del usuario:")
    if [ -n "$usuario" ]; then
        sudo adduser "$usuario"
    fi
}

eliminar_usuario() {
    usuario=$(zenity --entry --title="Eliminar usuario" --text="Introduce el nombre del usuario:")
    if [ -n "$usuario" ]; then
        sudo deluser "$usuario"
    fi
}

crear_grupo() {
    grupo=$(zenity --entry --title="Crear grupo" --text="Introduce el nombre del grupo:")
    if [ -n "$grupo" ]; then
        sudo addgroup "$grupo"
    fi
}

eliminar_grupo() {
    grupo=$(zenity --entry --title="Eliminar grupo" --text="Introduce el nombre del grupo:")
    if [ -n "$grupo" ]; then
        sudo delgroup "$grupo"
    fi
}

agregar_usuario_a_grupo() {
    usuario=$(zenity --entry --title="Agregar usuario a grupo" --text="Introduce el nombre del usuario:")
    grupo=$(zenity --entry --title="Agregar usuario a grupo" --text="Introduce el nombre del grupo:")
    if [ -n "$usuario" ] && [ -n "$grupo" ]; then
        sudo adduser "$usuario" "$grupo"
    fi
}

eliminar_usuario_de_grupo() {
    usuario=$(zenity --entry --title="Eliminar usuario de grupo" --text="Introduce el nombre del usuario:")
    grupo=$(zenity --entry --title="Eliminar usuario de grupo" --text="Introduce el nombre del grupo:")
    if [ -n "$usuario" ] && [ -n "$grupo" ]; then
        sudo deluser "$usuario" "$grupo"
    fi
}

cambiar_permisos() {
    ruta=$(zenity --entry --title="Cambiar permisos" --text="Introduce la ruta del archivo o directorio:")
    permisos=$(zenity --entry --title="Cambiar permisos" --text="Introduce los nuevos permisos (en formato numérico):")
    if [ -n "$ruta" ] && [ -n "$permisos" ]; then
        sudo chmod "$permisos" "$ruta"
    fi
}

# Mostrar comandos de Linux
mostrar_comandos() {
    opciones=$(for i in "${!comandos[@]}"; do echo "${comandos[$i]}"; done)
    opcion=$(zenity --list --title="Comandos de Linux más usados" --column="Comandos" $opciones)

    if [ -n "$opcion" ]; then
        cmd=$(echo $opcion | cut -d ' ' -f 1)
        $cmd
    fi
}

# Menú principal
while true; do
    opcion_principal=$(zenity --list --title="Menú principal" --column="Opción" --hide-header \
        "Comandos de Linux más usados" "Administración de usuarios y grupos" "Salir")

    case $opcion_principal in
        "Comandos de Linux más usados") mostrar_comandos ;;
        "Administración de usuarios y grupos")
            while true; do
                opcion_admin=$(zenity --list --title="Administración de usuarios y grupos" --column="Opción" --hide-header \
                    "Crear usuario" "Eliminar usuario" "Crear grupo" "Eliminar grupo" "Agregar usuario a grupo" "Eliminar usuario de grupo" "Cambiar permisos de archivo o directorio" "Volver")

                case $opcion_admin en
                    "Crear usuario") crear_usuario ;;
                    "Eliminar usuario") eliminar_usuario ;;
