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
## EP6 — Services y systemd (daemons)

### Gestión de servicios
- `sudo systemctl start <servicio>` — iniciar un servicio
- `sudo systemctl stop <servicio>` — detener un servicio
- `sudo systemctl restart <servicio>` — reiniciar un servicio
- `sudo systemctl reload <servicio>` — recargar config sin reiniciar
- `sudo systemctl status <servicio>` — ver estado y logs recientes
- `sudo systemctl enable <servicio>` — arrancar automáticamente al boot
- `sudo systemctl disable <servicio>` — no arrancar al boot
- `sudo systemctl enable --now <servicio>` — enable + start en un comando

### Listar servicios
- `systemctl list-units` — servicios activos
- `systemctl list-units --all` — todos (activos e inactivos)
- `systemctl list-unit-files` — archivos de unidad disponibles
- `systemctl list-units | grep <nombre>` — filtrar por nombre

### Conceptos clave
- **Daemon** — proceso en segundo plano que ofrece un servicio (sshd, httpd, chronyd)
- **.service vs .socket** — un servicio puede activarse por socket (bajo demanda) o por servicio directo
- **systemd** — el sistema de init moderno en Linux, reemplaza al sysv legacy

### Ejemplos prácticos
```bash
# Detener SSH (cuidado en remoto)
sudo systemctl stop ssh

# Ver si Apache está corriendo
sudo systemctl status httpd

# Hacer que firewalld arranque al boot y se prenda ahora
sudo systemctl enable --now firewalld
```
