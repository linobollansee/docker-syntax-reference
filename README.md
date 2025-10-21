# Docker Syntax Reference (Sorted by Frequency)

| Syntax / Keyword | Description | Freq | Example |
|------------------|--------------|------|----------|
| `docker build -t <name> .` | Builds a Docker image from a Dockerfile in the current directory | VC | `docker build -t myapp .` |
| `docker run <image>` | Runs a container from an image | VC | `docker run myapp` |
| `docker ps` | Lists running containers | VC | `docker ps` |
| `docker ps -a` | Lists all containers (running + stopped) | VC | `docker ps -a` |
| `docker images` | Lists all local images | VC | `docker images` |
| `docker pull <image>` | Downloads an image from a registry | VC | `docker pull ubuntu:latest` |
| `docker push <image>` | Uploads an image to a registry | VC | `docker push myuser/myapp:latest` |
| `docker stop <container>` | Stops a running container | VC | `docker stop myapp-container` |
| `docker start <container>` | Starts a stopped container | VC | `docker start myapp-container` |
| `docker rm <container>` | Removes a container | VC | `docker rm myapp-container` |
| `docker rmi <image>` | Removes an image | VC | `docker rmi myapp:latest` |
| `docker exec -it <container> bash` | Opens an interactive shell in a running container | VC | `docker exec -it web bash` |
| `docker logs <container>` | Displays logs from a container | VC | `docker logs myapp-container` |
| `docker-compose up` | Starts services from \`docker-compose.yml\` | VC | `docker-compose up -d` |
| `docker-compose down` | Stops and removes compose services | VC | `docker-compose down` |
| `docker-compose build` | Builds or rebuilds compose services | VC | `docker-compose build` |
| `FROM <base-image>` | Base image for a Dockerfile | VC | `FROM node:20-alpine` |
| `RUN <command>` | Runs commands at build time | VC | `RUN apt-get update && apt-get install -y git` |
| `COPY <src> <dest>` | Copies files from context into image | VC | `COPY . /app` |
| `WORKDIR <path>` | Sets working directory | VC | `WORKDIR /app` |
| `CMD ["cmd", "arg1", ...]` | Default command when container runs | VC | `CMD ["npm", "start"]` |
| `EXPOSE <port>` | Declares a listening port | VC | `EXPOSE 8080` |
| `ENV <key>=<value>` | Sets environment variables | VC | `ENV NODE_ENV=production` |
| `docker network ls` | Lists Docker networks | C | `docker network ls` |
| `docker network create <name>` | Creates a network | C | `docker network create mynet` |
| `docker volume ls` | Lists volumes | C | `docker volume ls` |
| `docker volume create <name>` | Creates a volume | C | `docker volume create data_vol` |
| `docker inspect <container or image>` | Shows detailed configuration | C | `docker inspect myapp` |
| `docker stats` | Displays resource usage of containers | C | `docker stats` |
| `docker tag <source> <target>` | Tags an image | C | `docker tag myapp myuser/myapp:v1` |
| `docker system prune` | Removes unused data | C | `docker system prune -f` |
| `ENTRYPOINT ["cmd", "arg1", ...]` | Configures executable container entrypoint | C | `ENTRYPOINT ["python3", "app.py"]` |
| `ARG <name>=<default>` | Build-time variable definition | C | `ARG NODE_VERSION=20` |
| `LABEL <key>=<value>` | Adds image metadata | C | `LABEL maintainer="marc@example.com"` |
| `docker login` / `docker logout` | Authenticates to or logs out from a registry | C | `docker login -u user` |
| `docker save` / `docker load` | Exports or imports images as tar archives | C | `docker save myapp > myapp.tar` |
| `docker cp <src> <dest>` | Copies files between host and container | C | `docker cp myapp:/var/log /tmp/logs` |
| `docker attach <container>` | Attaches to a running container’s console | C | `docker attach myapp` |
| `docker rename <old> <new>` | Renames a container | C | `docker rename old_container new_container` |
| `docker buildx build` | Advanced image builder for multi-architecture builds | LC | `docker buildx build --platform linux/arm64 -t myapp .` |
| `HEALTHCHECK CMD <command>` | Defines a container health check | LC | `HEALTHCHECK CMD curl -f http://localhost:8080 \|\| exit 1` |
| `USER <name or uid>` | Sets the user for subsequent commands | LC | `USER node` |
| `VOLUME ["path"]` | Declares a mount point | LC | `VOLUME ["/data"]` |
| `ONBUILD <command>` | Adds trigger instruction for child images | LC | `ONBUILD COPY . /app` |
| `docker history <image>` | Shows image layers and build history | LC | `docker history myapp:latest` |
| `docker diff <container>` | Shows filesystem changes in a container | LC | `docker diff myapp` |
| `docker commit <container> <image>` | Creates an image from container changes | LC | `docker commit myapp updated-myapp` |
| `docker top <container>` | Displays running processes inside a container | LC | `docker top myapp` |
| `docker port <container>` | Lists port mappings for a container | LC | `docker port myapp` |
| `docker save -o <file> <image>` | Saves an image as a tar file | LC | `docker save -o myapp.tar myapp:latest` |
| `docker load -i <file>` | Loads an image from a tar file | LC | `docker load -i myapp.tar` |
| `STOPSIGNAL <signal>` | Sets signal used to stop container | R | `STOPSIGNAL SIGTERM` |
| `SHELL ["cmd", "arg"]` | Changes default shell used in RUN commands | R | `SHELL ["powershell", "-Command"]` |
| `ADD <src> <dest>` | Copies files (like COPY) but can extract archives and fetch URLs | R | `ADD app.tar.gz /app` |
| `docker save --output <file> <image>` | Alternative syntax for saving image | R | `docker save --output image.tar myapp` |
| `docker import` / `docker export` | Imports or exports containers as tar archives | R | `docker export myapp > container.tar` |
| `docker checkpoint create` / `docker restore` | Experimental: snapshot and restore container state | R | `docker checkpoint create myapp snap1` |
| `docker swarm init` / `docker join` | Initializes or joins a Docker Swarm cluster | R | `docker swarm init` |
| `docker service create` / `docker ls` / `docker rm` | Manages services in Docker Swarm mode | R | `docker service ls` |
