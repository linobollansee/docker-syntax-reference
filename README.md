# Docker Syntax Reference (Sorted by Frequency)

| Syntax / Keyword | Description | Freq | Example |
|------------------|--------------|------|----------|
| **docker build -t \<name\> .** | Builds a Docker image from a Dockerfile in the current directory | VC | `docker build -t myapp .` |
| **docker run \<image\>** | Runs a container from an image | VC | `docker run myapp` |
| **docker ps** | Lists running containers | VC | `docker ps` |
| **docker ps -a** | Lists all containers (running + stopped) | VC | `docker ps -a` |
| **docker images** | Lists all local images | VC | `docker images` |
| **docker pull \<image\>** | Downloads an image from Docker Hub or another registry | VC | `docker pull ubuntu:latest` |
| **docker push \<image\>** | Uploads an image to Docker Hub or another registry | VC | `docker push myuser/myapp:latest` |
| **docker stop \<container\>** | Stops a running container | VC | `docker stop myapp-container` |
| **docker start \<container\>** | Starts a stopped container | VC | `docker start myapp-container` |
| **docker rm \<container\>** | Removes a container | VC | `docker rm myapp-container` |
| **docker rmi \<image\>** | Removes an image | VC | `docker rmi myapp:latest` |
| **docker exec -it \<container\> bash** | Executes an interactive shell inside a running container | VC | `docker exec -it web bash` |
| **docker logs \<container\>** | Displays logs from a container | VC | `docker logs myapp-container` |
| **docker-compose up** | Starts all services defined in `docker-compose.yml` | VC | `docker-compose up -d` |
| **docker-compose down** | Stops and removes all services defined in `docker-compose.yml` | VC | `docker-compose down` |
| **docker-compose build** | Builds or rebuilds services in a compose file | VC | `docker-compose build` |
| **FROM \<base-image\>** | Defines the base image for a Dockerfile | VC | `FROM node:20-alpine` |
| **RUN \<command\>** | Executes commands during image build | VC | `RUN apt-get update && apt-get install -y git` |
| **COPY \<src\> \<dest\>** | Copies files/folders from local context into the image | VC | `COPY . /app` |
| **WORKDIR \<path\>** | Sets the working directory inside the image | VC | `WORKDIR /app` |
| **CMD ["cmd", "arg1", ...]** | Default command executed when container runs | VC | `CMD ["npm", "start"]` |
| **EXPOSE \<port\>** | Declares which port the container listens on | VC | `EXPOSE 8080` |
| **ENV \<key\>=\<value\>** | Sets environment variables | VC | `ENV NODE_ENV=production` |
| **docker network ls** | Lists available Docker networks | C | `docker network ls` |
| **docker network create \<name\>** | Creates a new Docker network | C | `docker network create mynet` |
| **docker volume ls** | Lists all Docker volumes | C | `docker volume ls` |
| **docker volume create \<name\>** | Creates a new Docker volume | C | `docker volume create data_vol` |
| **docker inspect \<container|image\>** | Shows detailed configuration for a container or image | C | `docker inspect myapp` |
| **docker stats** | Displays resource usage statistics for containers | C | `docker stats` |
| **docker tag \<src\> \<target\>** | Tags an image for repository upload | C | `docker tag myapp myuser/myapp:v1` |
| **docker system prune** | Removes unused data (containers, images, networks) | C | `docker system prune -f` |
| **ENTRYPOINT ["cmd", "arg1", ...]** | Configures a container to run as an executable | C | `ENTRYPOINT ["python3", "app.py"]` |
| **ARG \<name\>=\<default\>** | Defines build-time variables | C | `ARG NODE_VERSION=20` |
| **LABEL \<key\>=\<value\>** | Adds metadata to an image | C | `LABEL maintainer="marc@example.com"` |
| **docker login / docker logout** | Authenticates or logs out from a registry | C | `docker login -u user -p pass` |
| **docker save / docker load** | Exports or imports images as tar archives | C | `docker save myapp > myapp.tar` |
| **docker cp \<src\> \<dest\>** | Copies files between container and host | C | `docker cp myapp:/var/log /tmp/logs` |
| **docker attach \<container\>** | Attaches to a running container’s console | C | `docker attach myapp` |
| **docker rename \<old\> \<new\>** | Renames a container | C | `docker rename old_container new_container` |
| **docker buildx build** | Advanced image builder for multi-architecture builds | LC | `docker buildx build --platform linux/arm64 -t myapp .` |
| **HEALTHCHECK CMD \<command\>** | Defines a command to test container health | LC | `HEALTHCHECK CMD curl -f http://localhost:8080 || exit 1` |
| **USER \<name|uid\>** | Sets the user for running subsequent commands | LC | `USER node` |
| **VOLUME ["path"]** | Declares a mount point for external volumes | LC | `VOLUME ["/data"]` |
| **ONBUILD \<command\>** | Adds a trigger instruction for child images | LC | `ONBUILD COPY . /app` |
| **docker history \<image\>** | Shows image layers and build history | LC | `docker history myapp:latest` |
| **docker diff \<container\>** | Shows changes to container filesystem | LC | `docker diff myapp` |
| **docker commit \<container\> \<image\>** | Creates a new image from a container’s changes | LC | `docker commit myapp updated-myapp` |
| **docker top \<container\>** | Displays running processes inside a container | LC | `docker top myapp` |
| **docker port \<container\>** | Lists port mappings for a container | LC | `docker port myapp` |
| **docker save -o \<file\> \<image\>** | Saves an image as a tar file | LC | `docker save -o myapp.tar myapp:latest` |
| **docker load -i \<file\>** | Loads an image from a tar file | LC | `docker load -i myapp.tar` |
| **STOPSIGNAL \<signal\>** | Sets system call signal used to stop container | R | `STOPSIGNAL SIGTERM` |
| **SHELL ["cmd", "arg"]** | Changes the default shell used in RUN commands | R | `SHELL ["powershell", "-Command"]` |
| **ADD \<src\> \<dest\>** | Copies files like `COPY` but can extract archives and fetch URLs | R | `ADD app.tar.gz /app` |
| **docker save --output** | Alternative syntax for exporting an image | R | `docker save --output image.tar myapp` |
| **docker import / docker export** | Imports or exports containers as tar archives | R | `docker export myapp > container.tar` |
| **docker checkpoint create / restore** | Experimental: snapshot and restore container state | R | `docker checkpoint create myapp snap1` |
| **docker swarm init / join** | Initializes or joins a Docker Swarm cluster | R | `docker swarm init` |
| **docker service create / ls / rm** | Manages services in Docker Swarm mode | R | `docker service ls` |

