# Dockermentation

Proyecto de auto-ayuda para documentar los comandos de docker.

## Documentos

1. INSTALAR.md
2. IMAGENES.md
3. CONTENEDORES.md
4. DOCKERFILE_ESTRUCTURA.md
5. PORTAINER.md

## Uso de docker

### Utilizar postgresql

1. Crear contenedor postgres_test con clave 12345678

```bash
sudo docker run --name postgres_test -e POSTGRES_PASSWORD=12345678 -d postgres
```

2. Conectar a linux de contenedor

```bash
sudo docker exec -it [id contenedor] /bin/bash
```

3. Conectar a psql

```bash
su postgres
psql
```
