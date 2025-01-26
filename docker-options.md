### 100 Unique Docker Troubleshooting and Interview Questions

#### Docker Basics

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
   **Explanation:** **docker version** provides detailed version information for the Docker client and server.

3. **What is the default storage driver for Docker on Linux?**  
   **A.** overlay2  
   **B.** aufs  
   **C.** devicemapper  
   **D.** zfs  
   **Correct Answer:** A. overlay2  
   **Explanation:** On most Linux distributions, **overlay2** is the default and preferred storage driver due to its performance and reliability.

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
   **Explanation:** The **docker container prune** command removes all stopped containers.

6. **What is the difference between **docker stop** and **docker kill**?**  
   **A.** **docker stop** kills processes, while **docker kill** sends termination signals  
   **B.** **docker stop** sends termination signals, while **docker kill** forcibly stops containers  
   **C.** Both commands are identical  
   **D.** **docker kill** pauses containers, while **docker stop** restarts them  
   **Correct Answer:** B. **docker stop** sends termination signals, while **docker kill** forcibly stops containers  
   **Explanation:** **docker stop** allows processes to terminate gracefully, whereas **docker kill** halts them immediately.

7. **Which flag is used to run a container in detached mode?**  
   **A.** -i  
   **B.** -t  
   **C.** -d  
   **D.** -rm  
   **Correct Answer:** C. -d  
   **Explanation:** The **-d** flag runs the container in detached mode, allowing it to run in the background.

8. **What is the purpose of **docker exec**?**  
   **A.** Execute commands on the Docker host  
   **B.** Execute commands inside a running container  
   **C.** Start a new container  
   **D.** Build a Docker image  
   **Correct Answer:** B. Execute commands inside a running container  
   **Explanation:** The **docker exec** command allows you to run a command inside an existing container.

#### Docker Images

9. **What command is used to create a new image from a Dockerfile?**  
   **A.** docker create  
   **B.** docker build  
   **C.** docker compile  
   **D.** docker init  
   **Correct Answer:** B. docker build  
   **Explanation:** The **docker build** command is used to build an image from a Dockerfile.

10. **How can you list all locally available Docker images?**  
    **A.** docker list images  
    **B.** docker images  
    **C.** docker show images  
    **D.** docker display  
    **Correct Answer:** B. docker images  
    **Explanation:** The **docker images** command displays all locally stored Docker images.

11. **What command would you use to remove an image by its ID?**  
    **A.** docker image delete  
    **B.** docker rmi  
    **C.** docker rm -i  
    **D.** docker image remove  
    **Correct Answer:** B. docker rmi  
    **Explanation:** The **docker rmi** command removes images using their ID or name.

12. **Which of the following options caches intermediate steps in a Docker build?**  
    **A.** --cache  
    **B.** --intermediate  
    **C.** --no-cache  
    **D.** Default behavior of **docker build**  
    **Correct Answer:** D. Default behavior of **docker build**  
    **Explanation:** Docker caches intermediate steps by default to speed up builds.

#### Docker Networking

13. **How do you inspect the network configuration of a running container?**  
    **A.** docker inspect <container_id>  
    **B.** docker network inspect <container_id>  
    **C.** docker network status <container_id>  
    **D.** docker container network <container_id>  
    **Correct Answer:** A. docker inspect <container_id>  
    **Explanation:** The **docker inspect** command provides detailed information, including network configuration.

...

Would you like me to generate the full set of 100 questions now?
