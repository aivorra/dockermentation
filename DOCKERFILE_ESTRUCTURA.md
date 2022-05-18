# DOCKERFILE

Estructura de archivo Dockerfile

## Estructura
```
FROM: imagen base utilizada.
LABEL: Nombre e email del creador.
RUN: ejecutar comandos antes de crear la imagen.
ENV: definir variables de entorno.
ADD/COPY: agregar o copiar archivos de la PC local al contenedor.
EXPOSE: exponer un puerto por defecto para el contenedor.
CMD: ejecutar comando por defecto al crear el contenedor.
```

## Comandos para Dockerfile

### Crear imagen en función del archivo Dockerfile

```bash
docker build -t <nombre de imagen> <directorio del archivo Dockerfile>
```

### Poner nombre y tag a una imagen

```bash
docker image tag <imagen id> <nombre de imagen>:<tag>
```