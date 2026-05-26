# 🐧 Linux Notes — NetworkChuck Course

## EP1 — Introducción
- `pwd` — muestra directorio actual
- `ls` — lista archivos
- `cd <dir>` — navegar a directorio
- `cd ..` — subir un nivel
- `cd .` — quedarse en el mismo directorio
- `clear` — limpiar terminal

## EP2 — Filesystem
- `cat /etc/os-release` — info del sistema
- Estructura raíz `/`:
  - `/etc` — configuraciones del sistema
  - `/var` — logs y datos variables
  - `/home` — carpetas de usuarios
  - `/bin` — comandos básicos
  - `/tmp` — archivos temporales
  - `/proc` — procesos del sistema

## EP3 — Manejo de archivos
- `cp <origen> <destino>` — copiar archivo
- `mv <origen> <destino>` — mover o renombrar
- `rm <archivo>` — borrar archivo
- `rmdir <dir>` — borrar directorio vacío
- `rm -r <dir>` — borrar directorio con contenido
- `sudo` — ejecutar como superusuario
- `sudo su` — entrar como root
- `su - <usuario>` — cambiar de usuario
- `man <comando>` — manual del comando
- `apropos <término>` — buscar comandos por descripción

## EP4 — Usuarios y permisos
- `sudo adduser <nombre>` — crear usuario completo
- `sudo useradd <nombre> -m` — crear usuario con home
- `sudo passwd <usuario>` — asignar contraseña
- `sudo usermod -l <nuevo> <viejo>` — renombrar usuario
- `sudo usermod --shell /bin/bash <usuario>` — cambiar shell
- `sudo usermod -aG <grupo> <usuario>` — agregar a grupo
- `sudo userdel <usuario>` — borrar usuario
- `sudo gpasswd -d <usuario> <grupo>` — quitar de grupo
- `sudo visudo` — editar permisos sudo
- `cat /etc/passwd` — lista de usuarios
- `sudo cat /etc/shadow` — contraseñas hasheadas

## EP5 — Package Management
- `sudo apt install <paquete>` — instalar paquete
- `sudo apt update` — actualizar lista de paquetes
- `sudo apt upgrade` — actualizar paquetes instalados
- `sudo apt update && sudo apt upgrade` — actualizar todo
- `apt search <término>` — buscar paquete
- `apt list --installed` — listar paquetes instalados
- `apt list --installed | grep <nombre>` — filtrar instalados
- `sudo dpkg -i <archivo.deb>` — instalar .deb manual
- `sudo snap install <paquete>` — instalar via snap
- `pip3 install -r requirements.txt --break-system-packages` — instalar dependencias Python
- `curl -I <url>` — ver headers HTTP de un sitio
