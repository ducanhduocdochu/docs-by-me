# 🐳 **Docker Commands: A Comprehensive Guide**

Docker is an open-source platform that helps you automate the deployment of applications inside containers. Containers allow you to package an application with all its dependencies, making it easy to manage and scale. Below is a detailed guide of commonly used Docker commands, complete with descriptions and examples to help you understand how to use them effectively.

---

## 🛠️ **Basic Docker Commands**

### **1. Check Docker Version**
- **`docker --version`**: Displays the current version of Docker installed on your system.
  - **Example**:
    ```bash
    $ docker --version
    ```
    Output:
    ```
    Docker version 20.10.7, build f0df350
    ```
    **Description**: Use this command to check if Docker is installed and to view the version. This is helpful for troubleshooting and ensuring compatibility.

### **2. Display System-wide Docker Information**
- **`docker info`**: Provides detailed system information about Docker, including containers, images, storage, and more.
  - **Example**:
    ```bash
    $ docker info
    ```
    **Description**: Displays important information such as the number of running containers, images, Docker storage driver, and other key details of your Docker setup.

### **3. Display Help for Docker Commands**
- **`docker help`**: Provides help information and usage instructions for Docker commands.
  - **Example**:
    ```bash
    $ docker help
    ```
    **Description**: Use this command to explore all available Docker commands and options. It’s a handy reference for beginners or when you need to recall the usage of specific commands.

---

## 📦 **Working with Docker Images**

### **1. List All Docker Images**
- **`docker images`**: Lists all Docker images that are stored on your system.
  - **Example**:
    ```bash
    $ docker images
    ```
    **Description**: This command shows a list of all the Docker images that have been pulled or created, along with their repository name, tag, image ID, and size.

### **2. Pull a Docker Image**
- **`docker pull <image>`**: Downloads a Docker image from Docker Hub or another Docker registry.
  - **Example**:
    ```bash
    $ docker pull nginx
    ```
    **Description**: This pulls the latest version of the `nginx` image from Docker Hub. The image will be saved locally, allowing you to run containers based on that image.

### **3. Build a Docker Image**
- **`docker build -t <image_name> .`**: Builds a Docker image from a Dockerfile in the current directory.
  - **Example**:
    ```bash
    $ docker build -t my_app .
    ```
    **Description**: This creates a new Docker image named `my_app` by reading the instructions in the Dockerfile found in the current directory.

### **4. Remove a Docker Image**
- **`docker rmi <image>`**: Deletes a Docker image from your system.
  - **Example**:
    ```bash
    $ docker rmi nginx
    ```
    **Description**: This command removes a Docker image from your system. It’s useful for freeing up space or cleaning up unused images.

### **5. Tag a Docker Image**
- **`docker tag <image> <repository:tag>`**: Adds a tag to a Docker image, usually in preparation for uploading to a Docker registry.
  - **Example**:
    ```bash
    $ docker tag my_app myrepo/my_app:v1
    ```
    **Description**: Tagging an image is important when you’re preparing to push it to a registry. Here, the image `my_app` is tagged as `v1` for uploading to the `myrepo` registry.

### **6. Push a Docker Image to a Registry**
- **`docker push <repository:tag>`**: Uploads a tagged image to a Docker registry like Docker Hub.
  - **Example**:
    ```bash
    $ docker push myrepo/my_app:v1
    ```
    **Description**: This pushes the image `my_app:v1` to the specified registry, making it available for others to download or deploy.

---

## 🚀 **Working with Docker Containers**

### **1. List Running Containers**
- **`docker ps`**: Displays a list of all currently running Docker containers.
  - **Example**:
    ```bash
    $ docker ps
    ```
    **Description**: Shows details about running containers, including container ID, image name, status, and ports.

### **2. List All Containers (Including Stopped)**
- **`docker ps -a`**: Lists all containers, both running and stopped.
  - **Example**:
    ```bash
    $ docker ps -a
    ```
    **Description**: This command shows all containers, whether they are running, stopped, or exited. It’s useful for troubleshooting and managing containers that are no longer running.

### **3. Run a Container**
- **`docker run <image>`**: Creates and starts a new container from an image.
  - **Example**:
    ```bash
    $ docker run nginx
    ```
    **Description**: This will start an `nginx` container. If the image isn’t available locally, Docker will pull it from the registry.

### **4. Run a Container in Detached Mode**
- **`docker run -d <image>`**: Starts a container in the background (detached mode).
  - **Example**:
    ```bash
    $ docker run -d nginx
    ```
    **Description**: Detached mode is useful for running services like web servers. The container will run in the background, allowing you to continue using the terminal.

### **5. Run a Container Interactively with Bash**
- **`docker run -it <image> bash`**: Starts a container and opens an interactive Bash shell inside it.
  - **Example**:
    ```bash
    $ docker run -it ubuntu bash
    ```
    **Description**: This is ideal for testing or debugging inside a container. It starts a container and gives you a command-line interface to run commands within the container.

### **6. Access a Running Container’s Shell**
- **`docker exec -it <container_id> bash`**: Accesses the shell of a running container.
  - **Example**:
    ```bash
    $ docker exec -it <container_id> bash
    ```
    **Description**: This allows you to interact with a running container by opening a shell inside it, which is helpful for checking logs or making changes on the fly.

### **7. Stop a Running Container**
- **`docker stop <container_id>`**: Gracefully stops a running container.
  - **Example**:
    ```bash
    $ docker stop <container_id>
    ```
    **Description**: This sends a SIGTERM signal to the container, allowing it to stop gracefully before shutting down.

### **8. Start a Stopped Container**
- **`docker start <container_id>`**: Starts a container that was previously stopped.
  - **Example**:
    ```bash
    $ docker start <container_id>
    ```
    **Description**: Restarts a container that is in a stopped state without having to create a new one.

### **9. Restart a Container**
- **`docker restart <container_id>`**: Stops and then starts a container, effectively rebooting it.
  - **Example**:
    ```bash
    $ docker restart <container_id>
    ```
    **Description**: This is useful for applying changes to a running container or resolving temporary issues without destroying the container.

### **10. Kill a Running Container**
- **`docker kill <container_id>`**: Immediately stops a running container.
  - **Example**:
    ```bash
    $ docker kill <container_id>
    ```
    **Description**: This forcefully stops the container by sending a SIGKILL signal, which is faster but doesn’t allow the container to gracefully shut down.

### **11. Remove a Stopped Container**
- **`docker rm <container_id>`**: Deletes a container that is no longer running.
  - **Example**:
    ```bash
    $ docker rm <container_id>
    ```
    **Description**: This removes a stopped container from your system, freeing up resources.

### **12. View Logs from a Container**
- **`docker logs <container_id>`**: Displays the logs of a running or stopped container.
  - **Example**:
    ```bash
    $ docker logs <container_id>
    ```
    **Description**: Use this to view the output logs of a container, which is helpful for debugging issues or tracking container activity.

### **13. Inspect a Container**
- **`docker inspect <container_id>`**: Provides detailed information about a container’s configuration, network, and environment.
  - **Example**:
    ```bash
    $ docker inspect <container_id>
    ```
    **Description**: This command gives low-level details about the container, such as its network settings, environment variables, volumes, and more.

---

## 🔧 **Networking and Volumes**

### **1. List Available Docker Networks**
- **`docker network ls`**: Displays all networks created in Docker.
  - **Example**:
    ```bash
    $ docker network ls
    ```
    **Description**: Docker networks allow containers to communicate with each other. This command lists all the available networks, including the default bridge network.

### **2. Create a New Docker Network**
- **`docker network create <network_name>`**: Creates a new custom Docker network.
  - **Example**:
    ```bash
    $ docker network create my_network
    ```
    **Description**: This creates a custom network that you can use to connect multiple containers for communication.

### **3. Connect a Container to a Network**
- **`docker network connect <network> <container>`**: Attaches a running container to a specified network.
  - **Example**:
    ```bash
    $ docker network connect my_network <container_id>
    ```
    **Description**: Use this to connect a container to an existing network, enabling it to communicate with other containers on the same network.

### **4. Disconnect a Container from a Network**
- **`docker network disconnect <network> <container>`**: Detaches a container from a specified network.
  - **Example**:
    ```bash
    $ docker network disconnect my_network <container_id>
    ```
    **Description**: This disconnects the container from the network, isolating it from other containers.

### **5. List All Docker Volumes**
- **`docker volume ls`**: Lists all Docker volumes.
  - **Example**:
    ```bash
    $ docker volume ls
    ```
    **Description**: Volumes are used for persistent storage in Docker. This command shows all the volumes that have been created on your system.

### **6. Create a New Docker Volume**
- **`docker volume create <volume_name>`**: Creates a new persistent volume.
  - **Example**:
    ```bash
    $ docker volume create my_volume
    ```
    **Description**: Use this command to create a named volume that you can attach to containers for persistent data storage.

### **7. Remove a Docker Volume**
- **`docker volume rm <volume_name>`**: Deletes a specified volume from the system.
  - **Example**:
    ```bash
    $ docker volume rm my_volume
    ```
    **Description**: Removes the volume `my_volume` and any data stored in it. Be cautious when removing volumes as it deletes the stored data permanently.

---

📝 **Created by ducanhduocdochu**
