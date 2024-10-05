# 🐳 **Comprehensive Docker Compose Commands Guide**

Docker Compose is a tool for defining and running multi-container Docker applications. With a simple YAML file, you can configure your services, networks, and volumes. Docker Compose streamlines application orchestration, making it easier to develop, test, and deploy complex environments.

---

## 🛠️ **Basic Docker Compose Commands**

### **1. Start Services**
- **`docker-compose up`**: Starts and runs all services defined in the `docker-compose.yml` file.
  - **Example**:
    ```bash
    $ docker-compose up
    ```
    **Description**: This starts all services as defined in your `docker-compose.yml`. The containers will run in the foreground, and logs from all services will stream to your console.

### **2. Start Services in Detached Mode**
- **`docker-compose up -d`**: Runs services in detached mode (in the background).
  - **Example**:
    ```bash
    $ docker-compose up -d
    ```
    **Description**: This command runs all services in the background, allowing you to continue using your terminal. It's useful for running long-running services like web servers.

### **3. Stop Services**
- **`docker-compose stop`**: Stops running services without removing the containers.
  - **Example**:
    ```bash
    $ docker-compose stop
    ```
    **Description**: This stops the running containers but keeps their state, so you can restart them later without rebuilding.

### **4. Restart Services**
- **`docker-compose restart`**: Restarts all or specified services.
  - **Example**:
    ```bash
    $ docker-compose restart
    ```
    **Description**: Restarts services, stopping and starting them again to apply any changes or fix temporary issues.

### **5. Bring Down Services and Remove Containers**
- **`docker-compose down`**: Stops and removes containers, networks, and volumes.
  - **Example**:
    ```bash
    $ docker-compose down
    ```
    **Description**: This command stops all running containers and removes the networks and volumes created by `docker-compose up`.

- **`docker-compose down --volumes`**: Also removes any volumes created by `docker-compose`.
  - **Example**:
    ```bash
    $ docker-compose down --volumes
    ```
    **Description**: In addition to stopping the services, this will also remove named volumes, which can help free up disk space.

---

## 🔄 **Building and Rebuilding Services**

### **1. Build Services**
- **`docker-compose build`**: Builds or rebuilds the services defined in the `docker-compose.yml`.
  - **Example**:
    ```bash
    $ docker-compose build
    ```
    **Description**: Reads the `Dockerfile` for each service and builds the images. It is used when you have made changes to your `Dockerfile` or dependencies.

- **`docker-compose build --no-cache`**: Builds services without using the cache.
  - **Example**:
    ```bash
    $ docker-compose build --no-cache
    ```
    **Description**: This forces Docker to rebuild the image from scratch, ignoring any previously cached layers.

### **2. Pull Latest Images**
- **`docker-compose pull`**: Pulls the latest version of images defined in the `docker-compose.yml`.
  - **Example**:
    ```bash
    $ docker-compose pull
    ```
    **Description**: This fetches the latest version of the images from Docker Hub or any specified registry without running the services.

---

## 📜 **Inspecting and Viewing Logs**

### **1. View Service Logs**
- **`docker-compose logs`**: Displays the logs from all running services.
  - **Example**:
    ```bash
    $ docker-compose logs
    ```
    **Description**: Shows the logs of all services, useful for debugging issues and tracking the behavior of your containers.

- **`docker-compose logs -f`**: Follow the logs for all services in real-time.
  - **Example**:
    ```bash
    $ docker-compose logs -f
    ```
    **Description**: Continuously outputs the logs as they are generated, similar to `tail -f`, ideal for live monitoring.

### **2. View the Status of Containers**
- **`docker-compose ps`**: Lists the status of all containers defined in the `docker-compose.yml`.
  - **Example**:
    ```bash
    $ docker-compose ps
    ```
    **Description**: Shows a list of containers and their status (running, stopped, exited), along with information on port mappings and command execution.

### **3. Check the Configuration**
- **`docker-compose config`**: Validates and shows the configuration.
  - **Example**:
    ```bash
    $ docker-compose config
    ```
    **Description**: Validates the syntax of your `docker-compose.yml` and displays the resolved configuration, useful for catching issues in the Compose file.

---

## 🧑‍💻 **Running One-off Commands and Tasks**

### **1. Run a Command in a Service**
- **`docker-compose run <service_name> <command>`**: Runs a one-off command in a new container of a specific service.
  - **Example**:
    ```bash
    $ docker-compose run web python manage.py migrate
    ```
    **Description**: This runs a command inside a new container for the `web` service, often used for tasks like database migrations or testing.

### **2. Execute Commands in Running Containers**
- **`docker-compose exec <service_name> <command>`**: Executes a command inside a running container.
  - **Example**:
    ```bash
    $ docker-compose exec web bash
    ```
    **Description**: This is used to run commands inside an already running container, such as opening a shell to inspect the container or run commands directly.

---

## 🏗️ **Scaling Services**

### **1. Scale Services**
- **`docker-compose up --scale <service_name>=<number>`**: Scales a service to the specified number of instances.
  - **Example**:
    ```bash
    $ docker-compose up --scale web=3
    ```
    **Description**: This scales the `web` service to run three instances, useful for load balancing and ensuring high availability in production environments.

### **2. Stop or Remove a Scaled Service**
- **`docker-compose down`**: Stops and removes all scaled services.
  - **Example**:
    ```bash
    $ docker-compose down
    ```
    **Description**: This will stop and remove all the scaled instances of a service, returning the environment to its initial state.

---

## 🔧 **Cleaning Up and Maintenance**

### **1. Remove Stopped Containers**
- **`docker-compose rm`**: Removes stopped service containers.
  - **Example**:
    ```bash
    $ docker-compose rm
    ```
    **Description**: Deletes stopped containers, freeing up space and cleaning the environment.

### **2. Remove Images and Containers**
- **`docker-compose down --rmi all --volumes`**: Stops services, removes containers, and deletes all images and volumes.
  - **Example**:
    ```bash
    $ docker-compose down --rmi all --volumes
    ```
    **Description**: This completely cleans up your Docker environment, removing all containers, images, and volumes associated with your Compose file.

---

## 📊 **Working with Docker Compose in Production**

### **1. Use Environment Variables**
- **`docker-compose up`** (with `.env` file): Automatically loads environment variables from a `.env` file located in the same directory as the `docker-compose.yml`.
  - **Example**:
    ```yaml
    version: '3'
    services:
      web:
        image: nginx
        environment:
          - ENV_VAR=${SOME_ENV_VAR}
    ```
    **Description**: Compose files support environment variable substitution, making it easier to manage configurations across different environments (development, staging, production).

### **2. Set Resource Limits**
- **Docker Compose** allows you to define resource limits such as CPU and memory for each service.
  - **Example**:
    ```yaml
    version: '3'
    services:
      web:
        image: nginx
        deploy:
          resources:
            limits:
              cpus: "0.5"
              memory: 512M
    ```
    **Description**: This limits the CPU usage to 50% and the memory to 512MB for the `web` service, ensuring that no single container consumes too many resources.

---

## 📚 **Advanced Docker Compose Usage**

### **1. Docker Compose Override**
- **docker-compose.override.yml**: This file is automatically merged with the base `docker-compose.yml` when running `docker-compose`. It allows you to have environment-specific configurations.
  - **Example**:
    ```yaml
    version: '3'
    services:
      web:
        environment:
          - DEBUG=true
    ```
    **Description**: Overrides are useful when you want different settings for different environments (e.g., enabling `DEBUG` in development but disabling it in production).

### **2. Multiple Compose Files**
- **`docker-compose -f`**: Allows you to specify multiple Compose files to override or add to the base configuration.
  - **Example**:
    ```bash
    $ docker-compose -f docker-compose.yml -f docker-compose.prod.yml up
    ```
    **Description**: This combines the `docker-compose.yml` and `docker-compose.prod.yml` files, applying the configurations from both, useful for separating development and production environments.

---

## 🚀 **Key Takeaways**
- **Docker Compose** is a powerful tool for orchestrating multi-container applications, offering simplified management for services, networks, and volumes.
- The commands in this guide cover everything from starting services, scaling, building images, to cleaning up your environment.
- By mastering these commands, you’ll be able to develop, test, and deploy complex applications efficiently.

---

### How to Use This Guide:
- Copy this content into your `README.md` file for a comprehensive reference to Docker Compose commands.
- Each command is explained with examples, making it easy to follow and use in your projects.
- You can add project-specific notes or modify sections based on your team's workflows.

---
📝 **Created by ducanhduocdochu**
