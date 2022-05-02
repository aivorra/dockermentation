# INSTALL Docker

## Instalar docker para linux

Se utiliza el siguiente script para la instalación automática para Ubuntu.

[link](https://get.docker.com/)

1. Crear archivo "docker_installer.sh" con el contecnido del link anterior.
```bash
curl -k https://get.docker.com -o docker_installer.sh
```
2. Ejecutar script
```bash
sudo sh docker_installer.sh
```

## Aplicar permisos a usuario sin privilegios

Luego de leer un poco no se si es necesario hacer esto, ya que con sudo suficiente para trabajar con usuarios sin privilegios. Pero de todas maneras dejo la info a mano.

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


## Información de docker cliente y servidor
```bash
docker info
```
y
```bash
docker version
```