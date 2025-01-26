### 100 Unique Docker Troubleshooting and Interview Questions

1. **What is the primary purpose of Docker?**  
   **A.** Manage hardware resources  
   **B.** Automate software deployments using containers  
   **C.** Replace virtual machines  
   **D.** Monitor server performance  
   **Correct Answer:** B. Automate software deployments using containers  
   **Explanation:** Docker is designed to simplify and automate software deployments by using lightweight, portable containers.

2. **Which command is used to view Docker’s version?**  
   **A.** docker -v  
   **B.** docker version  
   **C.** docker info  
   **D.** docker config  
   **Correct Answer:** B. docker version  
   **Explanation:** `docker version` provides detailed version information for the Docker client and server.

3. **What is the default storage driver for Docker on Linux?**  
   **A.** overlay2  
   **B.** aufs  
   **C.** devicemapper  
   **D.** zfs  
   **Correct Answer:** A. overlay2  
   **Explanation:** On most Linux distributions, `overlay2` is the default and preferred storage driver due to its performance and reliability.

4. **Which Docker component is responsible for managing and running containers?**  
   **A.** Docker Compose  
   **B.** Docker Engine  
   **C.** Docker CLI  
   **D.** Docker Hub  
   **Correct Answer:** B. Docker Engine  
   **Explanation:** The Docker Engine is the core of Docker, responsible for building, running, and managing containers.

#### Working with Docker Commands

5. **How do you remove all stopped containers?**  
   **A.** docker container prune  
   **B.** docker container rm all  
   **C.** docker rm -a  
   **D.** docker clean  
   **Correct Answer:** A. docker container prune  
   **Explanation:** The "docker container prune" command removes all stopped containers.

6. **What is the difference between `docker stop` and `docker kill`?**  
   **A.** `docker stop` kills processes, while `docker kill` sends termination signals  
   **B.** `docker stop` sends termination signals, while `docker kill` forcibly stops containers  
   **C.** Both commands are identical  
   **D.** `docker kill` pauses containers, while `docker stop` restarts them  
   **Correct Answer:** B. `docker stop` sends termination signals, while `docker kill` forcibly stops containers  
   **Explanation:** `docker stop` allows processes to terminate gracefully, whereas `docker kill` halts them immediately.

7. **Which flag is used to run a container in detached mode?**  
   **A.** -i  
   **B.** -t  
   **C.** -d  
   **D.** -rm  
   **Correct Answer:** C. -d  
   **Explanation:** The `-d` flag runs the container in detached mode, allowing it to run in the background.

8. **What is the purpose of `docker exec`?**  
   **A.** Execute commands on the Docker host  
   **B.** Execute commands inside a running container  
   **C.** Start a new container  
   **D.** Build a Docker image  
   **Correct Answer:** B. Execute commands inside a running container  
   **Explanation:** The `docker exec` command allows you to run a command inside an existing container.

#### Docker Images

9. **What command is used to create a new image from a Dockerfile?**  
   **A.** docker create  
   **B.** docker build  
   **C.** docker compile  
   **D.** docker init  
   **Correct Answer:** B. docker build  
   **Explanation:** The `docker build` command is used to build an image from a Dockerfile.

10. **How can you list all locally available Docker images?**  
    **A.** docker list images  
    **B.** docker images  
    **C.** docker show images  
    **D.** docker display  
    **Correct Answer:** B. docker images  
    **Explanation:** The `docker images` command displays all locally stored Docker images.

11. **What command would you use to remove an image by its ID?**  
    **A.** docker image delete  
    **B.** docker rmi  
    **C.** docker rm -i  
    **D.** docker image remove  
    **Correct Answer:** B. docker rmi  
    **Explanation:** The `docker rmi` command removes images using their ID or name.

12. **Which of the following options caches intermediate steps in a Docker build?**  
    **A.** --cache  
    **B.** --intermediate  
    **C.** --no-cache  
    **D.** Default behavior of `docker build`  
    **Correct Answer:** D. Default behavior of `docker build`  
    **Explanation:** Docker caches intermediate steps by default to speed up builds.

#### Docker Networking

13. **How do you inspect the network configuration of a running container?**  
    **A.** docker inspect <container_id>  
    **B.** docker network inspect <container_id>  
    **C.** docker network status <container_id>  
    **D.** docker container network <container_id>  
    **Correct Answer:** A. docker inspect <container_id>  
    **Explanation:** The `docker inspect` command provides detailed information, including network configuration.

14. **Which network mode allows a container to share the host's network stack?**  
    **A.** bridge  
    **B.** host  
    **C.** overlay  
    **D.** none  
    **Correct Answer:** B. host  
    **Explanation:** The `host` network mode allows a container to use the same network stack as the host.

15. **What command is used to create a user-defined bridge network?**  
    **A.** docker bridge create  
    **B.** docker network create  
    **C.** docker create network  
    **D.** docker network init  
    **Correct Answer:** B. docker network create  
    **Explanation:** The `docker network create` command creates a user-defined network, such as a bridge network.

16. **How can you connect a running container to a network?**  
    **A.** docker network connect <network> <container>  
    **B.** docker connect network <container> <network>  
    **C.** docker attach <network> <container>  
    **D.** docker network attach <container> <network>  
    **Correct Answer:** A. docker network connect <network> <container>  
    **Explanation:** The `docker network connect` command attaches a running container to a specific network.

17. **Which Docker network type provides complete network isolation?**  
    **A.** bridge  
    **B.** host  
    **C.** overlay  
    **D.** none  
    **Correct Answer:** D. none  
    **Explanation:** The `none` network type disables all networking for the container, ensuring isolation.

#### Docker Volumes

18. **What command creates a volume in Docker?**  
    **A.** docker create volume  
    **B.** docker volume create  
    **C.** docker volume add  
    **D.** docker add volume  
    **Correct Answer:** B. docker volume create  
    **Explanation:** The `docker volume create` command creates a named volume for container storage.

19. **How can you list all Docker volumes?**  
    **A.** docker volume ls  
    **B.** docker list volumes  
    **C.** docker volumes  
    **D.** docker show volumes  
    **Correct Answer:** A. docker volume ls  
    **Explanation:** The `docker volume ls` command displays all existing volumes.

20. **How can you attach a volume to a container?**  
    **A.** Using the --attach option  
    **B.** Using the -v option with `docker run`  
    **C.** Using the --volume option with `docker start`  
    **D.** Using the --bind option  
    **Correct Answer:** B. Using the -v option with `docker run`  
    **Explanation:** The `-v` option specifies a volume to mount when starting a container.

21. **What happens when you use the `--rm` flag with `docker run`?**  
    **A.** The container stops gracefully  
    **B.** The container and its volume are removed automatically after stopping  
    **C.** Only the container is removed after stopping  
    **D.** The container is paused instead of removed  
    **Correct Answer:** C. Only the container is removed after stopping  
    **Explanation:** The `--rm` flag removes the container after it stops, but not its associated volumes.

#### Docker Compose

22. **Which file is used by Docker Compose to define services, networks, and volumes?**  
    **A.** compose.yaml  
    **B.** docker-compose.yaml  
    **C.** services.yaml  
    **D.** compose.yml  
    **Correct Answer:** B. docker-compose.yaml  
    **Explanation:** The default configuration file for Docker Compose is `docker-compose.yaml`.

23. **How do you start all services defined in a Docker Compose file?**  
    **A.** docker start compose  
    **B.** docker-compose start  
    **C.** docker-compose up  
    **D.** docker up services  
    **Correct Answer:** C. docker-compose up  
    **Explanation:** The `docker-compose up` command starts all services defined in the Compose file.

24. **What flag is used with `docker-compose up` to run services in the background?**  
    **A.** -d  
    **B.** -b  
    **C.** -bg  
    **D.** --daemon  
    **Correct Answer:** A. -d  
    **Explanation:** The `-d` flag runs Docker Compose services in detached mode.

25. **How do you stop and remove all services created by Docker Compose?**  
    **A.** docker-compose remove  
    **B.** docker-compose stop  
    **C.** docker-compose down  
    **D.** docker-compose halt  
    **Correct Answer:** C. docker-compose down  
    **Explanation:** The `docker-compose down` command stops and removes all services and networks created.

#### Docker Logs and Monitoring

26. **Which command retrieves logs from a running container?**  
    **A.** docker logs <container_id>  
    **B.** docker container logs <container_id>  
    **C.** docker view logs <container_id>  
    **D.** docker get logs <container_id>  
    **Correct Answer:** A. docker logs <container_id>  
    **Explanation:** The `docker logs` command retrieves logs for a specific container.

27. **How do you follow a container's logs in real-time?**  
    **A.** docker logs <container_id> --tail  
    **B.** docker logs <container_id> -f  
    **C.** docker container logs -real-time  
    **D.** docker logs -live <container_id>  
    **Correct Answer:** B. docker logs <container_id> -f  
    **Explanation:** The `-f` flag follows the logs of a container in real-time.

28. **What is the purpose of the `docker stats` command?**  
    **A.** View container CPU and memory usage  
    **B.** View container network performance  
    **C.** View Docker Engine resource usage  
    **D.** View disk usage by images  
    **Correct Answer:** A. View container CPU and memory usage  
    **Explanation:** The `docker stats` command shows resource usage statistics for running containers.
Got it! I’ll continue generating Docker-related questions without including Docker Compose topics. 

#### Docker Logs and Monitoring (continued)

29. **How can you view resource usage for all running containers?**  
    **A.** docker stats  
    **B.** docker logs --all  
    **C.** docker usage  
    **D.** docker monitor  
    **Correct Answer:** A. docker stats  
    **Explanation:** The `docker stats` command displays real-time resource usage (CPU, memory, etc.) for all running containers.

30. **Which flag is used with `docker logs` to show only the last N lines?**  
    **A.** --tail  
    **B.** --lines  
    **C.** -n  
    **D.** --last  
    **Correct Answer:** A. --tail  
    **Explanation:** The `--tail` flag specifies the number of recent log lines to display.

#### Docker Images (continued)

31. **How can you check the history of a Docker image?**  
    **A.** docker history <image_id>  
    **B.** docker image history <image_id>  
    **C.** docker inspect <image_id>  
    **D.** docker log <image_id>  
    **Correct Answer:** A. docker history <image_id>  
    **Explanation:** The `docker history` command shows the history of layers for an image.

32. **Which command helps you clean up dangling images?**  
    **A.** docker image prune  
    **B.** docker clean images  
    **C.** docker rmi dangling  
    **D.** docker prune  
    **Correct Answer:** A. docker image prune  
    **Explanation:** The `docker image prune` command removes dangling images to free up disk space.

33. **What does the `docker pull` command do?**  
    **A.** Downloads an image from Docker Hub  
    **B.** Uploads an image to Docker Hub  
    **C.** Updates an existing container  
    **D.** Downloads a container from Docker Hub  
    **Correct Answer:** A. Downloads an image from Docker Hub  
    **Explanation:** The `docker pull` command fetches an image from a remote registry like Docker Hub.

34. **Which of the following commands helps tag an image?**  
    **A.** docker tag <image_id> <new_tag>  
    **B.** docker rename <image_id> <new_tag>  
    **C.** docker image tag <image_id> <new_tag>  
    **D.** Both A and C  
    **Correct Answer:** D. Both A and C  
    **Explanation:** The `docker tag` and `docker image tag` commands are interchangeable for tagging images.
    
36. **How do you rename an existing container?**  
    **A.** docker container rename <old_name> <new_name>  
    **B.** docker rename <old_name> <new_name>  
    **C.** docker container change <old_name> <new_name>  
    **D.** docker name change <old_name> <new_name>  
    **Correct Answer:** B. docker rename <old_name> <new_name>  
    **Explanation:** The `docker rename` command changes the name of an existing container.

37. **What happens if you try to remove a running container?**  
    **A.** It is removed immediately  
    **B.** Docker returns an error  
    **C.** The container is stopped and then removed  
    **D.** Docker prompts you for confirmation  
    **Correct Answer:** B. Docker returns an error  
    **Explanation:** Docker prevents the removal of running containers unless explicitly stopped.

38. **Which option can you use to allocate a pseudo-TTY to a container?**  
    **A.** -i  
    **B.** -t  
    **C.** -it  
    **D.** Both B and C  
    **Correct Answer:** D. Both B and C  
    **Explanation:** The `-t` option allocates a pseudo-TTY, and `-it` combines interactive and TTY modes.

39. **How can you log in to a private Docker registry?**  
    **A.** docker login <registry_url>  
    **B.** docker registry login <registry_url>  
    **C.** docker connect <registry_url>  
    **D.** docker auth <registry_url>  
    **Correct Answer:** A. docker login <registry_url>  
    **Explanation:** The `docker login` command authenticates with a private Docker registry.

40. **Which file stores Docker daemon configuration on Linux?**  
    **A.** /etc/docker/daemon.conf  
    **B.** /var/docker/config.json  
    **C.** /etc/docker/config.json  
    **D.** /usr/local/docker/daemon.cfg  
    **Correct Answer:** A. /etc/docker/daemon.conf  
    **Explanation:** The Docker daemon configuration is stored in `/etc/docker/daemon.conf` on Linux systems.

41. **What is the default port used by Docker Registry?**  
    **A.** 2375  
    **B.** 5000  
    **C.** 8080  
    **D.** 443  
    **Correct Answer:** B. 5000  
    **Explanation:** Docker Registry runs on port `5000` by default.

42. **How can you scan a Docker image for vulnerabilities?**  
    **A.** docker image scan  
    **B.** docker scan <image_id>  
    **C.** docker secure <image_id>  
    **D.** docker inspect --vulnerabilities <image_id>  
    **Correct Answer:** B. docker scan <image_id>  
    **Explanation:** The `docker scan` command scans images for security vulnerabilities.

43. **Which command shows all Docker events in real-time?**  
    **A.** docker events  
    **B.** docker log events  
    **C.** docker watch events  
    **D.** docker stream events  
    **Correct Answer:** A. docker events  
    **Explanation:** The `docker events` command streams real-time events from the Docker daemon.

44. **What is the default base image used when no `FROM` is specified in a Dockerfile?**  
    **A.** debian:latest  
    **B.** ubuntu:latest  
    **C.** scratch  
    **D.** alpine  
    **Correct Answer:** C. scratch  
    **Explanation:** The `scratch` image is an empty base image used when no specific base is provided.
    
46. **Which of the following is used to create a Docker network that spans multiple Docker hosts?**  
    **A.** bridge  
    **B.** overlay  
    **C.** host  
    **D.** none  
    **Correct Answer:** B. overlay  
    **Explanation:** The `overlay` network driver allows containers to communicate across multiple Docker hosts.

47. **What is the command to disconnect a container from a network?**  
    **A.** docker network disconnect  
    **B.** docker disconnect network  
    **C.** docker container disconnect  
    **D.** docker remove network  
    **Correct Answer:** A. docker network disconnect  
    **Explanation:** The `docker network disconnect` command removes a container from a network.

48. **Which Docker network mode creates a network bridge between the host and the container?**  
    **A.** bridge  
    **B.** host  
    **C.** none  
    **D.** container  
    **Correct Answer:** A. bridge  
    **Explanation:** The `bridge` mode creates a network bridge between the container and the host.

49. **Which command can you use to inspect the details of a Docker network?**  
    **A.** docker network info  
    **B.** docker network details  
    **C.** docker network inspect  
    **D.** docker network list  
    **Correct Answer:** C. docker network inspect  
    **Explanation:** The `docker network inspect` command shows details about a Docker network, including connected containers.
    
50. **What is the main advantage of using Docker volumes over bind mounts?**  
    **A.** Volumes are more portable and easier to manage  
    **B.** Volumes are faster than bind mounts  
    **C.** Bind mounts are read-only, while volumes are read-write  
    **D.** Volumes require less disk space  
    **Correct Answer:** A. Volumes are more portable and easier to manage  
    **Explanation:** Docker volumes provide a portable, managed storage solution, while bind mounts link directly to specific paths on the host filesystem.

51. **What is the command to list all volumes in Docker?**  
    **A.** docker volumes  
    **B.** docker volume list  
    **C.** docker volume ls  
    **D.** docker show volumes  
    **Correct Answer:** C. docker volume ls  
    **Explanation:** The `docker volume ls` command lists all available volumes in Docker.

52. **How can you inspect a volume's detailed information?**  
    **A.** docker volume info <volume_name>  
    **B.** docker inspect volume <volume_name>  
    **C.** docker volume inspect <volume_name>  
    **D.** docker show volume <volume_name>  
    **Correct Answer:** C. docker volume inspect <volume_name>  
    **Explanation:** The `docker volume inspect` command provides detailed information about a specific volume.

53. **What command is used to remove an unused Docker volume?**  
    **A.** docker volume delete <volume_name>  
    **B.** docker volume prune  
    **C.** docker rm volume <volume_name>  
    **D.** docker volume remove <volume_name>  
    **Correct Answer:** B. docker volume prune  
    **Explanation:** The `docker volume prune` command removes all unused volumes.

54. **Which of the following helps optimize Docker image builds?**  
    **A.** Reduce the number of layers in the Dockerfile  
    **B.** Always use the `latest` tag  
    **C.** Avoid caching in the Dockerfile  
    **D.** Use as many RUN commands as possible  
    **Correct Answer:** A. Reduce the number of layers in the Dockerfile  
    **Explanation:** Minimizing layers in the Dockerfile can reduce the size of the image and improve build performance.

55. **How can you limit the CPU resources allocated to a Docker container?**  
    **A.** --cpu  
    **B.** --cpu-shares  
    **C.** --cpus  
    **D.** Both B and C  
    **Correct Answer:** D. Both B and C  
    **Explanation:** The `--cpu-shares` and `--cpus` options can be used to limit CPU resources for a container.

56. **What command would you use to limit the amount of memory allocated to a Docker container?**  
    **A.** --memory  
    **B.** --mem  
    **C.** --limit-memory  
    **D.** --ram  
    **Correct Answer:** A. --memory  
    **Explanation:** The `--memory` flag sets the maximum amount of memory a container can use.

57. **Which command limits the disk I/O of a Docker container?**  
    **A.** --io  
    **B.** --blkio  
    **C.** --disk  
    **D.** --io-block  
    **Correct Answer:** B. --blkio  
    **Explanation:** The `--blkio` option allows you to limit disk I/O for a Docker container.

57. **What is the purpose of Docker container health checks?**  
    **A.** To monitor the CPU usage of a container  
    **B.** To ensure that the container is still running  
    **C.** To check if the container is responding to requests  
    **D.** To monitor disk usage inside a container  
    **Correct Answer:** C. To check if the container is responding to requests  
    **Explanation:** Health checks verify whether a container is operating properly by running periodic commands.

58. **How can you set a health check for a container in a Dockerfile?**  
    **A.** HEALTHCHECK <command>  
    **B.** HEALTH <command>  
    **C.** CHECK <command>  
    **D.** CONTAINER-HEALTH <command>  
    **Correct Answer:** A. HEALTHCHECK <command>  
    **Explanation:** The `HEALTHCHECK` instruction in the Dockerfile specifies a command to test the container's health.

59. **What does the `docker inspect` command display regarding container health?**  
    **A.** Only resource usage statistics  
    **B.** Container logs  
    **C.** Health status and details of health checks  
    **D.** The current configuration of the container  
    **Correct Answer:** C. Health status and details of health checks  
    **Explanation:** `docker inspect` shows detailed information, including the health status and health check results of a container.

60. **What command is used to set a security profile for Docker containers?**  
    **A.** docker security set  
    **B.** docker security profile  
    **C.** docker run --security-opt  
    **D.** docker profile  
    **Correct Answer:** C. docker run --security-opt  
    **Explanation:** The `--security-opt` flag allows you to set security options for a container.

61. **What is the purpose of Docker's User Namespaces feature?**  
    **A.** To provide network isolation between containers  
    **B.** To run containers with non-root privileges  
    **C.** To manage Docker volumes more efficiently  
    **D.** To isolate Docker images  
    **Correct Answer:** B. To run containers with non-root privileges  
    **Explanation:** User Namespaces allow containers to be run with user IDs different from the host system's user IDs, enhancing security.

62. **What is the primary role of Docker's AppArmor?**  
    **A.** Managing Docker networks  
    **B.** Controlling the container's access to the host filesystem  
    **C.** Monitoring CPU usage of containers  
    **D.** Managing container resource allocation  
    **Correct Answer:** B. Controlling the container's access to the host filesystem  
    **Explanation:** AppArmor is a Linux kernel security module that restricts the actions containers can perform on the host system.

63. **Which command is used to restart a running container?**  
    **A.** docker restart <container_name>  
    **B.** docker run --restart <container_name>  
    **C.** docker container restart <container_name>  
    **D.** docker container start --restart <container_name>  
    **Correct Answer:** A. docker restart <container_name>  
    **Explanation:** The `docker restart` command is used to restart a running container.

64. **Which command helps you remove a Docker container forcefully?**  
    **A.** docker rm -f <container_name>  
    **B.** docker container remove --force <container_name>  
    **C.** docker kill <container_name>  
    **D.** docker remove -f <container_name>  
    **Correct Answer:** A. docker rm -f <container_name>  
    **Explanation:** The `-f` option forces the removal of a container, even if it is running.

65. **How can you check the Docker daemon’s status?**  
    **A.** systemctl status docker  
    **B.** docker status  
    **C.** docker daemon status  
    **D.** docker info  
    **Correct Answer:** A. systemctl status docker  
    **Explanation:** `systemctl status docker` shows the current status of the Docker daemon.

66. **What does the `docker info` command display?**  
    **A.** Details about the Docker containers and images  
    **B.** Information about Docker installation and system-wide settings  
    **C.** Logs of Docker operations  
    **D.** The health status of Docker containers  
    **Correct Answer:** B. Information about Docker installation and system-wide settings  
    **Explanation:** The `docker info` command provides information about Docker’s system-wide configuration, including version, network drivers, and more.

67. **Which cloud provider's CLI integrates with Docker for deploying containers?**  
    **A.** AWS CLI  
    **B.** Azure CLI  
    **C.** Google Cloud SDK  
    **D.** All of the above  
    **Correct Answer:** D. All of the above  
    **Explanation:** AWS, Azure, and Google Cloud all provide CLIs that integrate with Docker for container deployment.

68. **How do you configure Docker to use a specific registry for pulling images?**  
    **A.** docker registry set <registry_url>  
    **B.** docker login --registry <registry_url>  
    **C.** docker login <registry_url>  
    **D.** docker pull --registry <registry_url>  
    **Correct Answer:** C. docker login <registry_url>  
    **Explanation:** The `docker login` command allows you to authenticate to a specific registry before pulling images.

69. **Which command allows you to deploy Docker containers to AWS ECS?**  
    **A.** docker ecs deploy  
    **B.** aws ecs deploy  
    **C.** ecs-cli compose up  
    **D.** docker ecs run  
    **Correct Answer:** C. ecs-cli compose up  
    **Explanation:** The `ecs-cli compose up` command deploys Docker containers to Amazon Elastic Container Service (ECS).

70. **What does the `docker inspect` command do?**  
    **A.** Provides detailed information about a container or image  
    **B.** Inspects the system’s overall Docker configuration  
    **C.** Shows the logs of a container  
    **D.** Provides real-time stats about Docker containers  
    **Correct Answer:** A. Provides detailed information about a container or image  
    **Explanation:** The `docker inspect` command provides low-level information about containers or images in JSON format.

71. **Which command would you use to troubleshoot why a Docker container is not starting?**  
    **A.** docker inspect <container_name>  
    **B.** docker ps -a  
    **C.** docker logs <container_name>  
    **D.** docker start --debug <container_name>  
    **Correct Answer:** C. docker logs <container_name>  
    **Explanation:** The `docker logs` command provides the container’s logs, which can help diagnose why it isn’t starting.

72. **What is the first thing you should check if a container is consuming too much CPU?**  
    **A.** Check the Docker image  
    **B.** Check the logs of the container  
    **C.** Verify the resource limits set for the container  
    **D.** Restart the container  
    **Correct Answer:** C. Verify the resource limits set for the container  
    **Explanation:** Resource limits (e.g., CPU) set during container startup can prevent excessive resource consumption.

73. **Which of the following is a common reason for a "Cannot connect to Docker daemon" error?**  
    **A.** Docker service is not running  
    **B.** Incorrect Docker configuration file  
    **C.** Docker image is corrupted  
    **D.** Network connectivity issue  
    **Correct Answer:** A. Docker service is not running  
    **Explanation:** This error typically occurs when the Docker daemon is not running on the system.

74. **If a Docker container is unable to access a host’s local directory, which of the following might be the cause?**  
    **A.** Container lacks the necessary permissions to access the host directory  
    **B.** The container is running out of memory  
    **C.** The volume mount path is incorrect  
    **D.** The network mode is misconfigured  
    **Correct Answer:** A. Container lacks the necessary permissions to access the host directory  
    **Explanation:** If the container does not have proper permissions to access the mounted directory, it cannot interact with it.

75. **What is the best practice for reducing the size of Docker images?**  
    **A.** Use the `latest` tag  
    **B.** Minimize the number of layers by combining commands  
    **C.** Include unnecessary files in the image for flexibility  
    **D.** Use a larger base image  
    **Correct Answer:** B. Minimize the number of layers by combining commands  
    **Explanation:** Combining RUN, COPY, and ADD commands can reduce the number of layers and decrease the image size.

76. **Which is a best practice when writing a Dockerfile for a production environment?**  
    **A.** Use the `latest` image tag  
    **B.** Install unnecessary packages for debugging  
    **C.** Minimize the number of layers  
    **D.** Use a single large RUN command  
    **Correct Answer:** C. Minimize the number of layers  
    **Explanation:** To create efficient and secure images, it's best to minimize the number of layers in production Dockerfiles.

77. **What is a common mistake when setting up Docker containers for production?**  
    **A.** Leaving unnecessary ports open  
    **B.** Running containers with root privileges  
    **C.** Not monitoring resource usage  
    **D.** All of the above  
    **Correct Answer:** D. All of the above  
    **Explanation:** Insecure configurations like open ports, root privileges, and lack of resource monitoring are common mistakes in production environments.

78. **Which command is used to follow the real-time logs of a running Docker container?**  
    **A.** docker logs -f <container_name>  
    **B.** docker tail -f <container_name>  
    **C.** docker logs --follow <container_name>  
    **D.** docker monitor logs <container_name>  
    **Correct Answer:** A. docker logs -f <container_name>  
    **Explanation:** The `-f` flag allows you to follow the logs of a container in real-time.

79. **How can you view the last 100 lines of logs for a container?**  
    **A.** docker logs --tail 100 <container_name>  
    **B.** docker logs --lines 100 <container_name>  
    **C.** docker logs -n 100 <container_name>  
    **D.** docker logs --last 100 <container_name>  
    **Correct Answer:** A. docker logs --tail 100 <container_name>  
    **Explanation:** The `--tail` option limits the logs to the last N lines.

80. **What command is used to stream the stats of a running container?**  
    **A.** docker stats <container_name>  
    **B.** docker monitor stats <container_name>  
    **C.** docker stats --follow <container_name>  
    **D.** docker stream stats <container_name>  
    **Correct Answer:** A. docker stats <container_name>  
    **Explanation:** The `docker stats` command provides real-time statistics on CPU, memory, and network usage for containers.

81. **Which Docker command shows the system-wide usage of Docker images, containers, and volumes?**  
    **A.** docker system status  
    **B.** docker system df  
    **C.** docker system info  
    **D.** docker usage  
    **Correct Answer:** B. docker system df  
    **Explanation:** The `docker system df` command shows disk usage of images, containers, volumes, and build cache.

82. **Which command is used to initialize a Docker Swarm cluster?**  
    **A.** docker swarm init  
    **B.** docker swarm create  
    **C.** docker swarm start  
    **D.** docker swarm deploy  
    **Correct Answer:** A. docker swarm init  
    **Explanation:** The `docker swarm init` command initializes a new Swarm cluster on the current node.

83. **How can you add a node to an existing Docker Swarm cluster?**  
    **A.** docker swarm join --token <token> <manager_ip>  
    **B.** docker swarm add --token <token> <manager_ip>  
    **C.** docker node add --token <token> <manager_ip>  
    **D.** docker join swarm --manager <manager_ip>  
    **Correct Answer:** A. docker swarm join --token <token> <manager_ip>  
    **Explanation:** The `docker swarm join` command adds a node to an existing Swarm cluster using a join token.

84. **What command is used to create a service in Docker Swarm?**  
    **A.** docker service create  
    **B.** docker swarm service create  
    **C.** docker create service  
    **D.** docker service deploy  
    **Correct Answer:** A. docker service create  
    **Explanation:** The `docker service create` command is used to create a service in Docker Swarm.

85. **How can you scale a Docker Swarm service?**  
    **A.** docker service scale <service_name>=<replica_count>  
    **B.** docker service update --replicas <replica_count> <service_name>  
    **C.** docker service scale --replicas <replica_count> <service_name>  
    **D.** docker swarm scale <service_name> <replica_count>  
    **Correct Answer:** B. docker service update --replicas <replica_count> <service_name>  
    **Explanation:** The `docker service update --replicas` command is used to scale the number of replicas for a service in Docker Swarm.

86. **What command is used to list the nodes in a Docker Swarm cluster?**  
    **A.** docker swarm node ls  
    **B.** docker node list  
    **C.** docker swarm nodes  
    **D.** docker node ls  
    **Correct Answer:** D. docker node ls  
    **Explanation:** The `docker node ls` command lists all nodes in a Docker Swarm cluster.

87. **Which of the following is a Docker security best practice for handling sensitive data?**  
    **A.** Store sensitive data directly in Dockerfiles  
    **B.** Use environment variables for sensitive data  
    **C.** Include secrets as part of the image  
    **D.** Store sensitive data in the container’s logs  
    **Correct Answer:** B. Use environment variables for sensitive data  
    **Explanation:** Environment variables provide a secure way to manage sensitive data like passwords without hardcoding them into the image.

88. **Which command allows you to scan Docker images for vulnerabilities?**  
    **A.** docker scan <image_name>  
    **B.** docker image scan <image_name>  
    **C.** docker vulnerability scan <image_name>  
    **D.** docker security scan <image_name>  
    **Correct Answer:** A. docker scan <image_name>  
    **Explanation:** The `docker scan` command scans Docker images for security vulnerabilities, using tools like Snyk.

89. **What feature in Docker helps mitigate container breakout vulnerabilities?**  
    **A.** SELinux  
    **B.** AppArmor  
    **C.** User namespaces  
    **D.** All of the above  
    **Correct Answer:** D. All of the above  
    **Explanation:** SELinux, AppArmor, and user namespaces are security features that help protect against container breakout vulnerabilities.

90. **Which Docker feature can limit container access to the host filesystem?**  
    **A.** Capabilities  
    **B.** Volumes  
    **C.** Seccomp profiles  
    **D.** Read-only file systems  
    **Correct Answer:** D. Read-only file systems  
    **Explanation:** Making the container’s filesystem read-only prevents it from modifying the host filesystem.

91. **Which command is used to remove unused Docker images, containers, volumes, and networks?**  
    **A.** docker system prune  
    **B.** docker cleanup prune  
    **C.** docker remove unused  
    **D.** docker clean system  
    **Correct Answer:** A. docker system prune  
    **Explanation:** The `docker system prune` command removes all unused images, containers, volumes, and networks.

92. **What is the command to remove all stopped containers?**  
    **A.** docker container prune  
    **B.** docker rm -a  
    **C.** docker rm --all  
    **D.** docker container remove --all  
    **Correct Answer:** A. docker container prune  
    **Explanation:** The `docker container prune` command removes all stopped containers.

93. **What command is used to remove unused Docker volumes?**  
    **A.** docker volume prune  
    **B.** docker remove volumes  
    **C.** docker volume rm  
    **D.** docker delete unused volumes  
    **Correct Answer:** A. docker volume prune  
    **Explanation:** The `docker volume prune` command removes all unused volumes from the system.

94. **Which command is used to list all Docker networks on the system?**  
    **A.** docker network ls  
    **B.** docker networks list  
    **C.** docker show networks  
    **D.** docker network show  
    **Correct Answer:** A. docker network ls  
    **Explanation:** The `docker network ls` command lists all Docker networks currently available on the system.

95. **What type of Docker network is isolated to a single host and not accessible from outside?**  
    **A.** bridge  
    **B.** host  
    **C.** overlay  
    **D.** none  
    **Correct Answer:** A. bridge  
    **Explanation:** The `bridge` network type is the default network for containers on a single host, and it is isolated from external networks.

96. **Which of the following is used to create a network that spans across multiple Docker hosts?**  
    **A.** overlay  
    **B.** bridge  
    **C.** host  
    **D.** none  
    **Correct Answer:** A. overlay  
    **Explanation:** The `overlay` network is used to create multi-host networks in Docker Swarm and Kubernetes environments.

97. **How do you connect a running container to a specific Docker network?**  
    **A.** docker network connect <network_name> <container_name>  
    **B.** docker container connect <container_name> <network_name>  
    **C.** docker attach network <network_name> <container_name>  
    **D.** docker network attach <container_name> <network_name>  
    **Correct Answer:** A. docker network connect <network_name> <container_name>  
    **Explanation:** The `docker network connect` command is used to attach a running container to a network.

98. **What command is used to disconnect a container from a Docker network?**  
    **A.** docker network disconnect <network_name> <container_name>  
    **B.** docker container disconnect <network_name>  
    **C.** docker detach network <network_name> <container_name>  
    **D.** docker remove network <container_name>  
    **Correct Answer:** A. docker network disconnect <network_name> <container_name>  
    **Explanation:** The `docker network disconnect` command is used to disconnect a container from a network.

99. **What does the `docker history` command do?**  
    **A.** Shows the build history of a Docker image  
    **B.** Shows the logs of a Docker container  
    **C.** Shows the creation timestamp of Docker containers  
    **D.** Displays the history of the Docker service  
    **Correct Answer:** A. Shows the build history of a Docker image  
    **Explanation:** The `docker history` command shows the layers and timestamps of how a Docker image was built.

100. **What is the main purpose of Docker image layers?**  
    **A.** To store configuration files for the container  
    **B.** To allow for caching and efficient image builds  
    **C.** To track the version of the container  
    **D.** To separate the container’s code from its environment  
    **Correct Answer:** B. To allow for caching and efficient image builds  
    **Explanation:** Docker layers allow for efficient image building and caching, enabling faster builds and reusability of image components.
