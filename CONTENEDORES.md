# CONTENEDORES

Comandos para la gestión de contenedores.

## Run

### Crear y arrancar contenedor de imágen
```bash
docker run <imagen>
```

### Crear, arrancar, conectar en modo interactivo por terminal y definir nombre al contenedor
```bash
docker run --name <nombre de contenedor> -it <imagen>
```

### Crear, arrancar, desatachar y vincular puerto de PC local con puerto del contenedor
```bash
docker run -dp <peurto local>:<puerto contenedor> <imagen>
```

## Información de contenedores

### Listar contenedores con espacio de disco y estado
```bash
docker ps -sa
```

### Inforamción de la configuración del contenedor
```bash
docker inspect <contenedor id>
```

### Ver logs de contenedor
```bash
docker logs <contenedor id>
```

## Gestión de contenedores

### Arrancar y parar contenedor (ya existente)
```bash
docker start <contenedor id>
```
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

## Acceso a contenedores

### Conectar a contenedor por terminal en modo interactivo
```bash
docker exec -it <contenedor id> /bin/bash
```

### Conectar a la salida del contenedor en ejecución
```bash
docker attach <contenedor id>
```

### Salir del contenedor sin detenerlo (deatach)
```
Ctrl+P Ctrl+Q
```

## Volúmenes y archivos

### Listar volumenes
```bash
docker volume ls
```

### Muestra información del volume
```bash
docker volume inspect <volume name>
```

### Eliminar volume
```bash
docker volume rm <volume name>
```

### Vincular volumen de OS host con contenedor
```bash
docker run -v <directorio o archivo local>:<directorio o archivo en contenedor>:<permisos(ro/rw)> -d -p <imagen>
```

### Copiar archivo/directorio entre contenedor y PC local
```bash
docker container cp <contenedor id>:/<archivo-directorio> <archivo-directorio local>
```
o
```bash
docker container cp <archivo-directorio local> <contenedor id>:/<archivo-directorio>
```

## Redes

### Ver redes de los contenedores
```bash
docker network ls
```

### Muestra información de la configuración bridge
```bash
docker network inspect bridge
```

### Crear red para docker
```bash
docker network create <nombre de red>
```

### Añadir contenedor a red
```bash
docker network connect <nombre de red> <contenedor id>
```

### Desconectar contenedor de red
```bash
docker network disconnect <tipo de red> <contenedor id>
```