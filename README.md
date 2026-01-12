# Guía de Instalación Rápida de Docker en Debian 13

## ¿Qué es Docker?
Docker es una plataforma de código abierto que permite empaquetar aplicaciones en **contenedores**.  
Estos contenedores incluyen todo lo necesario para que una aplicación funcione (código, librerías, configuraciones), asegurando portabilidad, rapidez y eficiencia en cualquier entorno: desarrollo, pruebas o producción.

---

## Instalación y uso


# 1. Actualizar paquetes e instalar herramientas necesarias (ejecutar con usuario estándar)

su -c "apt update && apt upgrade"

su -c "apt install git -y"

su -c "apt-get install ca-certificates curl"

# 2. Clonar el repositorio, ingresar al directorio y dar permisos de ejecución al script

git clone https://github.com/Chelo2025/Docker

cd Docker

chmod +x docker-repo.sh

# 3. Ejecutar el script y luego instalar Docker y Docker Compose

su -c "./docker-repo.sh"

su -c "apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin"

# 4. Verificar el estado del servicio y añadirlo al arranque

su -c "systemctl --no-pager status docker && systemctl enable docker"

# (Opcional) Ejecutar Docker sin ser root

su -c "/usr/sbin/usermod -aG docker \"$(logname)\""

Nota: Para que este cambio sea efecto, debes cerrar tu sesión y volver a entrar.

# Prueba de instalación

docker run hello-world

# Autor

Marcelo Martinez - Chelo2025

🎓 Estudiante de Licenciatura en Tecnologías Digitales

🛡️ Técnico Superior en Redes Informáticas

🎓 Estudiante en Diplomado en Administración de Redes Linux con Orientación en Ciberseguridad y Ethical Hacking con Kali Linux
