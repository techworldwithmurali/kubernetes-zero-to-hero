### The Complete Docker Cheat Sheet for DevOps Engineers

This concise guide covers essential **Docker commands**, **Dockerfile instructions**, and best practices for managing containers, images, and networks. Perfect for developers and DevOps engineers, it’s your go-to reference for mastering Docker and streamlining your workflows.

| **Command**                          | **Description**                                                               |
|--------------------------------------|-------------------------------------------------------------------------------|
| `docker --version`                   | Show Docker version                                                           |
| `docker pull <image>`                | Pull an image from Docker Hub                                                 |
| `docker build -t <name> .`           | Build an image from a Dockerfile                                              |
| `docker images`                      | List all local Docker images                                                  |
| `docker rmi <image>`                 | Remove a Docker image                                                         |
| `docker ps`                          | List all running containers                                                  |
| `docker ps -a`                       | List all containers (including stopped)                                       |
| `docker run <image>`                 | Run a container from a specified image                                        |
| `docker run -d <image>`              | Run a container in detached mode                                              |
| `docker exec -it <container> bash`   | Run a command (bash) inside a running container                              |
| `docker stop <container>`            | Stop a running container                                                      |
| `docker start <container>`           | Start a stopped container                                                     |
| `docker restart <container>`         | Restart a running or stopped container                                        |
| `docker logs <container>`            | View logs of a container                                                      |
| `docker stats`                       | Show container resource usage (CPU, memory, etc.)                             |
| `docker network ls`                  | List all Docker networks                                                      |
| `docker volume ls`                   | List all Docker volumes                                                       |
| `docker inspect <container/image>`   | Get detailed information about a container or image                          |
| `docker-compose up`                  | Start services defined in a `docker-compose.yml` file                        |
| `docker-compose down`                | Stop and remove containers and networks defined in a `docker-compose.yml`     |
| `docker-compose build`               | Build or rebuild services defined in a `docker-compose.yml`                  |
| `docker-compose logs`                | View logs of services in a `docker-compose.yml`                               |
| `docker volume create <volume>`      | Create a new Docker volume                                                    |
| `docker run -v <volume>:<path>`      | Mount a volume to a container                                                 |
| `docker exec <container> <command>`  | Execute a command inside a running container                                  |
| `docker pull <image>:<tag>`          | Pull a specific tagged version of an image                                    |
| `docker push <image>`                | Push an image to Docker Hub                                                   |
| `docker login`                       | Log in to Docker Hub                                                          |
| `docker build -f <Dockerfile> .`         | Build an image from a custom Dockerfile                                         |
| `docker tag <image> <new_tag>`           | Tag an image with a new name or version                                        |
| `docker push <image>:<tag>`              | Push an image to a Docker registry (like Docker Hub)                           |
| `docker pull <image>:<tag>`              | Pull an image with a specific tag from a Docker registry                       |
| `docker cp <container>:<path> <host>`    | Copy files from a container to the host                                       |
| `docker cp <host> <container>:<path>`    | Copy files from the host to a container                                       |
| `docker volume inspect <volume>`         | Get detailed information about a Docker volume                                |
| `docker network inspect <network>`       | Get detailed information about a Docker network                               |
| `docker exec -u <user> <container> <cmd>`| Run a command as a different user inside a running container                   |
| `docker attach <container>`              | Attach to a running container to view its output and interact with it         |
| `docker-compose exec <service> <cmd>`    | Execute a command in a running service in a Docker Compose setup              |
| `docker-compose ps`                      | List containers in a Docker Compose environment                               |
| `docker-compose build --no-cache`        | Build images without using cache (fresh build)                                |
| `docker-compose up -d`                   | Start containers in detached mode in a Docker Compose setup                   |
| `docker-compose down --volumes`          | Stop and remove containers, networks, and volumes in Docker Compose setup     |
| `docker volume prune`                    | Remove all unused volumes                                                      |
| `docker network prune`                   | Remove all unused networks                                                     |
| `docker system prune`                    | Remove all unused containers, images, and networks                           |
| `docker system df`                       | Display disk usage of Docker objects (images, containers, volumes, networks)  |
| `docker info`                            | Display system-wide information about Docker                                  |
| `docker version`                         | Show version information for Docker CLI and server                           |
| `docker container rm <container>`        | Remove a stopped container                                                     |
| `docker container prune`                 | Remove all stopped containers                                                  |
| `docker image prune`                     | Remove all unused images                                                      |
| `docker-compose run --rm <service> <cmd>`| Run a one-off command in a Docker Compose service (remove after run)         |
| `docker attach <container>`              | Attach your terminal to a running container's standard input/output streams   |
| `docker exec -it <container> sh`         | Open a shell in a running container that doesn’t have bash                    |
| `docker stats <container>`               | Show real-time performance data for a container                               |
| `docker login <registry>`                | Log in to a custom Docker registry                                             |
| `docker logout`                          | Log out from Docker registry                                                   |
| `docker-compose pull`                         | Pull the latest version of images defined in `docker-compose.yml`             |
| `docker-compose up --build`                   | Build images before starting containers in a Docker Compose setup             |
| `docker-compose up --force-recreate`          | Recreate containers even if they already exist                               |
| `docker-compose up --no-deps <service>`       | Start a service without starting its dependencies in Docker Compose           |
| `docker-compose logs --follow`                | Follow the logs of containers in real time in a Docker Compose environment    |
| `docker-compose logs <service>`               | View logs of a specific service in a Docker Compose setup                     |
| `docker-compose scale <service>=<num>`        | Scale a service to a specific number of containers                            |
| `docker-compose config`                       | Validate and view the Docker Compose file                                    |
| `docker-compose restart <service>`            | Restart a specific service in a Docker Compose setup                         |
| `docker-compose stop`                         | Stop all services in a Docker Compose setup                                   |
| `docker-compose start`                        | Start all stopped services in a Docker Compose setup                          |
| `docker-compose pause`                        | Pause all running containers in a Docker Compose setup                        |
| `docker-compose unpause`                      | Unpause all paused containers in a Docker Compose setup                       |
| `docker logs -f <container>`                  | Follow logs of a specific container in real-time                              |
| `docker inspect -f '{{.State.Running}}' <container>` | Check if a container is running (returns true or false)              |
| `docker commit <container> <image>`           | Create a new image from a container’s changes                                  |
| `docker update --memory <size> <container>`   | Update the resource limits (e.g., memory) for a running container             |
| `docker rename <old_name> <new_name>`         | Rename a container or image                                                   |
| `docker save -o <path_to_file.tar> <image>`   | Save a Docker image to a tarball file                                          |
| `docker load -i <path_to_file.tar>`           | Load a Docker image from a tarball file                                        |
| `docker export <container> > <file.tar>`      | Export the filesystem of a container to a tarball                             |
| `docker import <file.tar>`                   | Import a tarball as a new Docker image                                         |
| `docker container top <container>`            | Show the running processes inside a container                                 |
| `docker inspect <container> --format '{{.NetworkSettings.IPAddress}}'` | Get the IP address of a container           |
| `docker network connect <network> <container>`| Connect a container to a Docker network                                        |
| `docker network disconnect <network> <container>`| Disconnect a container from a Docker network                                 |
| `docker system prune --all`                   | Remove all unused data (images, containers, networks, volumes)                |
| `docker volume rm <volume>`                   | Remove a specific Docker volume                                                |
| `docker network rm <network>`                 | Remove a specific Docker network                                               |
| `docker ps -q`                                | List only container IDs (quiet mode)                                           |
| `docker container ls -a`                      | List all containers (running and stopped)                                     |
| `docker inspect --format '{{.Id}}' <container>`| Retrieve the ID of a running container                                        |
| `docker info --format '{{.MemTotal}}'`        | Show the total system memory available for Docker                             |
| `docker run --name <container_name> <image>`  | Run a container with a custom name                                             |
| `docker run --rm <image>`                     | Run a container and remove it after it stops                                  |
| `docker stats --no-stream`                    | Show a snapshot of container resource usage (without streaming)               |
| `docker exec -it <container> pwd`             | Run the `pwd` command inside a running container                              |
| `docker exec -it <container> ls`              | Run the `ls` command inside a running container                               |
| `docker exec -it <container> cat <file>`      | View the contents of a file inside a running container                        |
| `docker exec -it <container> nano <file>`     | Edit a file inside a running container with `nano`                            |
| `docker logs --tail <number> <container>`     | View the last specified number of lines from a container's log               |
| `docker wait <container>`                     | Block until a container stops and then return its exit code                   |
| `docker events`                              | Stream real-time events from Docker (e.g., container start, stop, etc.)        |
| `docker system info`                         | Display detailed system-wide Docker information                               |
| `docker stats <container>`                   | Display real-time stats (CPU, memory, etc.) for a container                    |
| `docker exec -it <container> bash`           | Open a bash shell in a running container                                      |
| `docker exec -it <container> /bin/sh`        | Open a shell in a running container (if bash is not available)                 |
| `docker network create <network_name>`       | Create a custom Docker network                                                 |
| `docker network rm <network>`                | Remove a custom Docker network                                                 |
| `docker network ls`                          | List all Docker networks                                                       |
| `docker volume create <volume_name>`         | Create a named volume in Docker                                                |
| `docker volume rm <volume_name>`             | Remove a Docker volume                                                         |
| `docker volume prune`                        | Remove all unused Docker volumes                                               |
| `docker container prune`                     | Remove all stopped containers                                                  |
| `docker image prune`                         | Remove all unused images                                                       |
| `docker system prune --volumes`              | Remove all unused containers, networks, images, and volumes                    |
| `docker build --no-cache -t <image_name>`    | Build an image without using cache (fresh build)                               |
| `docker build -t <image_name> .`             | Build a Docker image from the current directory                               |
| `docker build -f <path_to_dockerfile> .`     | Build an image from a Dockerfile in a different location                       |
| `docker inspect --format '{{.State.Status}}' <container>` | Check if a container is running, paused, or stopped              |
| `docker stop $(docker ps -q)`                | Stop all running containers                                                     |
| `docker start $(docker ps -a -q)`            | Start all stopped containers                                                    |
| `docker kill <container>`                    | Forcefully stop a running container                                             |
| `docker rm -f <container>`                   | Force remove a running or stopped container                                     |
| `docker rename <old_name> <new_name>`        | Rename a container or image                                                     |
| `docker pull --all-tags <image>`             | Pull all tags (versions) of a Docker image from a registry                     |
| `docker tag <image> <repository>:<tag>`      | Tag an image with a new repository and tag                                      |
| `docker push <image>:<tag>`                  | Push an image with a specific tag to a Docker registry                         |
| `docker run --rm -p <host_port>:<container_port> <image>` | Run a container and map host port to container port                      |
| `docker run -v <host_path>:<container_path>` | Mount a volume from the host to a container                                     |
| `docker run --link <container_name>:<alias>` | Link a container to another container                                          |
| `docker run --env <key>=<value>`             | Set an environment variable in the container                                    |
| `docker run -e <env_var>=<value>`            | Set environment variables in a container during the run                        |
| `docker run --entrypoint <command>`          | Override the entry point of the container                                       |
| `docker run -it <image> /bin/bash`           | Run an interactive container with a bash shell                                 |
| `docker-compose exec <service> <command>`    | Execute a command in a running service inside a Docker Compose environment     |
| `docker-compose up --scale <service>=<num>`  | Scale a service to a specific number of instances in Docker Compose            |
| `docker-compose logs --tail <number>`        | Show the last specified number of logs from a service in Docker Compose        |
| `docker-compose ps`                          | List containers in a Docker Compose environment                               |
| `docker-compose up --remove-orphans`        | Start services and remove containers not defined in `docker-compose.yml`       |
| `docker-compose build --no-cache`            | Build the services in Docker Compose without cache                            |
| `docker-compose down --remove-orphans`      | Stop and remove all containers, networks, and volumes not defined in Docker Compose |
| `docker-compose stop <service>`              | Stop a specific service in Docker Compose                                      |
| `docker-compose restart <service>`           | Restart a specific service in Docker Compose                                   |
| `docker-compose pull <service>`              | Pull the image for a service defined in Docker Compose                         |
| `docker-compose up -d --build`               | Build images and start containers in detached mode                             |
| `docker-compose exec <service> bash`         | Open a bash shell in a specific service container in Docker Compose            |


## Dockerfile instructions to complement your Docker cheat sheet:

| **Instruction**        | **Description**                                                               |
|------------------------|-------------------------------------------------------------------------------|
| `FROM <image>`          | Defines the base image for the Docker image. It is the first instruction in a Dockerfile. |
| `RUN <command>`         | Executes a command during the image build process (e.g., installing packages).  |
| `CMD ["executable", "param1", "param2"]` | Specifies the default command to run when a container starts from the image (can be overridden). |
| `ENTRYPOINT ["executable", "param1"]`  | Sets the executable to run in the container and allows additional parameters to be passed to it. |
| `COPY <src> <dest>`     | Copies files or directories from the host to the container. `<src>` is relative to the build context, and `<dest>` is the path inside the container. |
| `ADD <src> <dest>`      | Similar to `COPY`, but also supports remote URLs and automatic unpacking of compressed files (like `.tar`). |
| `WORKDIR <path>`        | Sets the working directory for any subsequent `RUN`, `CMD`, `ENTRYPOINT`, `COPY`, and `ADD` instructions. |
| `ENV <key>=<value>`     | Sets an environment variable inside the container. It can be accessed during the container's execution. |
| `EXPOSE <port>`         | Informs Docker that the container listens on the specified network ports at runtime (does not actually publish the ports). |
| `VOLUME ["/path"]`      | Creates a mount point and marks it as holding externally stored data (e.g., persistent storage). |
| `USER <user>`           | Sets the user for the following instructions. Can be a username or UID, and an optional group can be specified. |
| `ARG <name>[=<default>]`| Defines build-time variables that can be passed using the `--build-arg` flag during the build process. |
| `LABEL <key>=<value>`   | Adds metadata to the image in the form of key-value pairs (useful for image documentation). |
| `STOPSIGNAL <signal>`   | Specifies the signal to be used to stop the container (e.g., SIGTERM). |
| `SHELL ["executable", "parameters"]` | Specifies the shell to be used for the `RUN` instructions (can be used to override the default shell). |
| `HEALTHCHECK`           | Specifies a command to run to check the health of the container and its status. |
