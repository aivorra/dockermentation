# CONTENEDORES

### Crear contenedor de imágen y lo enciende
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
docker run -dp <peurto local>:<puerto contenedor> <imágen>
```

### Conectar a contenedor por terminal en modo interactivo
```bash
docker exec --interactive --tty <contenedor id> /bin/bash
```
o
```bash
docker exec -it <contenedor id> /bin/bash
```

### Copiar archivo/directorio entre contenedor y PC local, y vice-versa
```bash
docker container cp <contenedor id>:/<archivo-directorio> <archivo-directorio local>
```
o
```bash
docker container cp <archivo-directorio local> <contenedor id>:/<archivo-directorio>
```