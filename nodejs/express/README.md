# NodeJS

## A quick express server

A quick static express server hosted on port 3000

### Building the image
```
docker build -t quick_express_docker .
```

### Commands and compose

Docker CLI
```bash
docker run -v <DIR_TO_PUBLIC_FILES>:/app/public -p <PORT_ACCESSIBLE_FROM_OUTSIDE_DOCKER>:3000 quick_express_docker
```

Docker Compose
```yml
version: '3.7'
services:
  quick_express_docker:
    container_name: quick_express_docker
    image: quick_express_docker
    restart: unless-stopped
    ports:
      - <PORT_ACCESSIBLE_FROM_OUTSIDE_DOCKER>:3000
    volumes:
      - <DIR_TO_PUBLIC_FILES>:/app/public
```

```
docker-compose -f <FILE_TO_COMPOSE> -d up
``` 
