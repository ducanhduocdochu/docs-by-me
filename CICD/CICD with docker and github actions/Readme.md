🌟 How to **CICD** for **Backend** so basic with **Docker**, **GitHub Action**, **Ubuntu Server**

> Hello guys, today, Ill be with you build CICD for application **Backend** with **Docker**, **Github Action**, **Ubuntu Server**. In that, Ill show you how to write **Dockerfile** for packing into containers, write file **Github Action workflow** for CI pipeline and CD pipeline to **Ubuntu Server**. From there, you can deploy more complex backend applications, with a foundation for **Docker compose**, **Kubernet**, **Jenkins**, **Gitlab** technologies.

---

# 🔍 1. What is CICD, what is Docker, GitHub Action and its uses?

- In order to not become a robot, before learning something new, I always want to know its uses, or basic definitions, sometimes I want to understand its uses very clearly, before I learn how to use it.

## 💻 CICD

- CI is the process of automatically integrating programmer's code source code into a branch in a version management system (like Git) on a regular basis.
- CD is astep further from CI, any successfully tested code changes are automatically deployed to the environment without manual intervention.
- Process (canbe):
+ Developers commit code to the version control system (maybe Git)
+ CI pipeline will examine all code, include test and build
+ If everything goes well, next to CD
+ CD pipeline will deploy to the development/production environment

## 🗂️ Docker
- Docker is an open source platform that allows you to automate application deployment in containers. Containers are lightweight, isolated environments that run applications along with all the necessary components (libraries, dependencies, configuration files, etc.) without needing to be installed on the host's operating system.
- Docker enables fast and consistent application deployment across a variety of environments.
- Docker is deployed into containers, containing full libraries, config, and dependencies
- Runs on any server with docker, helping to save resources and costs

## 📄 Github action
- GitHub Actions is a CI/CD (Continuous Integration/Continuous Delivery) service that integrates directly within GitHub, allowing you to automate software development processes, such as building, testing, and deploying applications immediately after release. There are changes in the source code repository. It supports creating "workflows" based on events such as code push, pull request, or release.
- Detail for github action: https://github.com/ducanhduocdochu/docs-by-me/blob/main/CICD/Github%20action/Readme.md

---

# 📱 2. Basic Pipeline CICD

<p align="center">
  <img src="https://github.com/ducanhduocdochu/docs-by-me/blob/main/CICD/CICD%20with%20docker%20and%20github%20actions/CICDdrawio.drawio.png" alt="overview" width="500"/>
</p>

- In here:
+ Automatically start the pipeline when there is a push or pull request event.
+ Build Docker image from source code.
+ Run tests.
+ If the build and test are successful, GitHub Actions will push the Docker image to Docker Hub (or ECR if using AWS).
+ Pull image from dockerhub to Ubuntu Server
+ Run image in Docker environment

# 🎨 3. Demo
- I will prepare a source code basic for backend include expose port and api get to get "Hello world"
``` javascript
require('dotenv').config();
const express = require('express');

const app = express();

app.get('/', (req, res) => {
  res.send('Hello World');
});

const PORT = process.env.PORT;
app.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}/`);
});
```
- Here is my source code structure, I will add env, a little enhancement in cicd implementation
<p align="center">
  <img src="https://github.com/ducanhduocdochu/docs-by-me/tree/main/CICD/CICD%20with%20docker%20and%20github%20actions" alt="overview" width="500"/>
</p>

- The first, i need dockerize project by DockerFile.
- Dockerfile is a text file containing scripts (commands and instructions) to build a Docker image. A Docker image is a file system clone that contains everything needed to run an application, including source code, libraries and dependencies, configuration files, and more.
``` Dockerfile
FROM node:18
WORKDIR /
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "app.js"]
```
- I will explain about this Dockerfile file.
+ **From node:18**: this command allows the environment inside the docker container to be nodejs version 18.
+ **WORKDIR /**: Allows the working directory to be the current directory performing dockerize.
+ C**OPY package*.json ./**: copy the entire package*.json file into the container, here are the dependencies.
+ **RUN npm install**: install dependencies based on the package*.json file.
+ **COPY ..**: copy the entire source code into the container.
+ **EXPOSE 3000**: opens port 3000 for the container.
+ **CMD ["node", "app.js"]**: Run the application'

More details in https://github.com/ducanhduocdochu/docs-by-me/tree/main/Docker/Docker%20File

- Next, I will proceed to create a repo on github with simple operations and link the local repo to my github.
More detail from github in https://github.com/ducanhduocdochu/docs-by-me/tree/main/Git.Github
- To deploy on github action, I need to build a folder .github/workflow/... Inside the folder will be the CICD pipelines that will be run. In this project, I will build CICD in one pipeline

- I will create newfile for pipeline in .github/workflow/... is cicd.yaml.
- <p align="center">
  <img src="https://github.com/ducanhduocdochu/docs-by-me/blob/main/CICD/CICD%20with%20docker%20and%20github%20actions/Screenshot%202024-10-13%20100954.png" width="500"/>
</p>

``` yaml
# Name pipeline
name: CI/CD pipeline
# Trigger for running job
on:
  # Run jobs when push code in branch main
  push:
    branches: [ main ] 

jobs:
  # Job 1: Build Docker image
  build:
    # Set up environment
    runs-on: ubuntu-latest
    steps:
      # Step 1: Check git
      - name: Checkout
        uses: actions/checkout@v2
      # Step 2: Set up Docker Buildx
      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v2

      # Step 3: Log in to Docker Hub
      - name: Log in to Docker Hub
        uses: docker/login-action@v2
        with:
          username: ${{ secrets.DOCKER_HUB_USERNAME }}
          password: ${{ secrets.DOCKER_HUB_ACCESS_TOKEN }}

      # Step 4: Set up cache 
      - name: Cache Docker Image Layers
        uses: actions/cache@v3
        with:
          path: /tmp/.buildx-cache
          key: $${{ runner.os }}-buildx-${{github.sha}}
          restore-keys: 
            ${{runner.os}}--buildx

      # Step 5: Push image to dockerhub
      - name: Build and Push Docker Image
        uses: docker/build-push-action@v5
        with:
          push: true
          tags: ${{ secrets.DOCKER_HUB_USERNAME }}/testCICD:latest
          cache-from: type=local,src=/tmp/.buildx-cache
          cache-to: type=local,dest=/tmp/.buildx-cache
  deploy:
    runs-on: ubuntu-latest
    needs: build  # Run affter building job "build" has finished
    steps:
      # Step 1: Connect SSH to server Ubuntu and pull image from Docker Hub
      - name: Deploy to Ubuntu server
        uses: appleboy/ssh-action@v0.1.2
        with:
          host: ${{ secrets.SERVER_HOST }}
          username: ubuntu
          key: ${{ secrets.SERVER_SSH_KEY }}
          script: |
            docker login -u ${{ secrets.DOCKER_HUB_USERNAME }} -p ${{ secrets.DOCKER_HUB_ACCESS_TOKEN }}
            docker pull ${{ secrets.DOCKER_HUB_USERNAME }}/my-app:latest
            docker stop my-app || true
            docker rm my-app || true
            docker run -d -p 80:80 --name my-app ${{ secrets.DOCKER_HUB_USERNAME }}/my-app:latest
```

- Next, Ill set up env secret in github. I choose setting in repo github and **secret and variables**. I have
<p align="center">
  <img src="https://github.com/ducanhduocdochu/docs-by-me/blob/main/CICD/CICD%20with%20docker%20and%20github%20actions/Screenshot%202024-10-13%20113703.png" width="500"/>
</p>

- In here, i need add DOCKER_HUB_USERNAME, DOCKER_HUB_ACCESS_TOKEN, PORT, SERVER_HOST, SERVER_SSH_KEY.
- Finally, lets push code and enjoy results.
<p align="center">
  <img src="https://github.com/ducanhduocdochu/docs-by-me/blob/main/CICD/CICD%20with%20docker%20and%20github%20actions/Screenshot%202024-10-13%20124635.png" width="500"/>
</p>
- You can see logs in here and debug if system error.

- Here is source code in my github: https://github.com/ducanhduocdochu/testcicd\

--- 

📝 **Created by ducanhduocdochu**

