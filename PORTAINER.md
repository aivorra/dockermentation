# PORTAINER.md

Instalación y configuración de portainer

[Link de referencia]:(https://docs.portainer.io/start/install-ce/server/docker/linux)

## Instalación

Crear volumen
```bash
docker volume create portainer_data
```
Descargar e instalar contenedor
```bash
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.21.3
```

## Chequear instalación

Ejecutar comando y ver algo similar a esto:
```bash
root@server:~# docker ps
CONTAINER ID   IMAGE                          COMMAND                  CREATED       STATUS      PORTS                                                                                  NAMES             
de5b28eb2fa9   portainer/portainer-ce:2.21.3  "/portainer"             2 weeks ago   Up 9 days   0.0.0.0:8000->8000/tcp, :::8000->8000/tcp, 0.0.0.0:9443->9443/tcp, :::9443->9443/tcp   portainer
```

## Acceder a Portainer

En un navegador web:

https://servidor:9443

## Troubleshooting

Reiniciar portainer
```bash
docker stop portainer
docker start portainer
```