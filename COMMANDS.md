# Docker

Documentaicón para utilizar en linux ubuntu 20.04

### Descargar docker para linux

[link](https://get.docker.com/)

1. Crear archivo "docker_installer.sh" con el contecnido del link anterior.
2. Aplicar permisos para ejecutar script
```bash
chmod 777 docker_installer.sh
```
3. Ejecutar script
```bash
./docker_installer.sh
```

### Dar permisos a usuario sin privilegios

En función al siguiente link: [link](https://docs.docker.com/engine/security/rootless/)

1. Ejecutar los siguietes comandos:
```bash
sudo apt-get install uidmap
sudo apt-get install  dbus-user-session
curl -fsSL https://get.docker.com/rootless | sh
systemctl --user enable docker
sudo loginctl enable-linger $(whoami)
```

2. Cerrar sesión e ingresar nuevamente con el mismo usuario al OS.

3. Verificar el correcto acceso a docker
```bash
docker version
```

4. Si el punto anterior no muestrar ningún error de permisos, obviar los siguentes pasos.

En función al siguiente link: [fix permission denied](https://www.digitalocean.com/community/questions/how-to-fix-docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket)

Ejecutar los siguientes comandos:
```bash
sudo groupadd docker
sudo usermod -aG docker ${USER}
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R
sudo systemctl restart docker
```

5. Verificar el correcto acceso a docker
```bash
docker version
docker info
```
Ahora no debería mostrar ningún error.

## Comandos básicos

### Información de docker
```bash
docker info
```
y
```bash
docker version
```

### Ver imágenes locales
```bash
docker images
```

### Buscar imágenes en hub.docker.com
```bash
docker search <palabra clave>:<tag>
```

### Descargar imágenes en hub.docker.com
```bash
docker pull <palabra clave>:<tag>
```

### Crear contenedor de imágen
```bash
docker run <iamgen>
```

### Listar contenedores y su estado
```bash
docker ps -a
```

### Parar contenedor
```bash
docker stop <contenedor id>
```

### Eliminar contenedor
```bash
docker rm <contenedor id>
```
o forzando parada de contenedor
```bash
docker rm <contenedor id> --force
```

### Crear contenedor, desatacharme y vincular puerto de PC local con puerto del contenedor
```bash
docker run --detach --publish <peurto local>:<puerto contenedor> <imágen>
```
o 
```bash
docker run --d --p <peurto local>:<puerto contenedor> <imágen>
```

### Conectar a contenedor por terminal de forna interactiva
```bash
docker exec --interactive --tty <contenedor id> /bin/bash
```

### Copiar archivo de contenedor a PC local
```bash
docker container cp <contenedor id>:/<directorio/archivo del contenedor> <directorio/archivo local>
```

### Copiar archivo de PC local a contenedor
```bash
docker container cp <directorio/archivo local> <contenedor id>:/<directorio/archivo del contenedor>
```

### Crear una imágen desde un contenedor
```bash
docker commit <contenedor id> <nombre de nueva imágen>
```

