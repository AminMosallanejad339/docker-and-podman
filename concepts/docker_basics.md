------

# 🐳 Docker Basics

This document contains my personal notes on **Docker fundamentals** for data engineering. 
It covers core concepts, common commands, and examples.

## 📦 What Is Docker?

Docker is an open-source platform that enables developers to build, ship, and run applications inside lightweight, portable containers. Containers package code, dependencies, and system tools together, ensuring consistency across environments.

- Docker is a **containerization platform**.  
- A **container** is a lightweight, isolated environment that runs applications and dependencies together.  
- Benefits:
  - Consistency across environments (works the same on dev, test, prod).
  - Lightweight compared to virtual machines.
  - Portable and reproducible setups for data engineering workflows.

## 🚀 Why Use Docker?

- **Portability**: Run your app anywhere—locally, on servers, or in the cloud.

- **Isolation**: Each container runs independently, avoiding conflicts.

- **Efficiency**: Containers are lightweight and start quickly.

- **Scalability**: Easily scale applications using Docker Compose or orchestration tools like Kubernetes.

  ## Common Use Cases

  1. Application packaging and deployment
  2. Microservices architecture
  3. Continuous Integration/Continuous Deployment (CI/CD)
  4. Development environment standardization
  5. Scalable cloud deployments

  ## Benefits

  - Portability across machines
  - Lightweight compared to VMs
  - Isolation of applications
  - Simplified configuration
  - Easier scaling
  - Better resource utilization

## 🔧 Key Concepts

| Concept        | Description                                                  |
| -------------- | ------------------------------------------------------------ |
| **Image**      | A snapshot of a container, including the app and its dependencies. |
| **Container**  | A running instance of an image.                              |
| **Dockerfile** | A script that defines how to build a Docker image.           |
| **Volume**     | Persistent storage for containers.                           |
| **Network**    | Allows containers to communicate with each other.            |

## 🏗️ Core Concepts

### 1. **Images**
- A **blueprint** for containers.
- Built from a `Dockerfile`.
- Stored in registries (e.g., Docker Hub).

### 2. **Containers**
- Running instances of images.
- They can be started, stopped, removed, or restarted.

### 3. **Dockerfile**
- Script that defines how to build an image.
- Example:
  ```dockerfile
  FROM python:3.9
  WORKDIR /app
  COPY requirements.txt .
  RUN pip install -r requirements.txt
  COPY . .
  CMD ["python", "main.py"]
  ```

### **4. Volumes**

Persistent storage for containers.

Useful for databases (PostgreSQL, MySQL).

### **5. Networks**

Allow containers to communicate.

Example: PostgreSQL + Airflow + Spark containers in one network.

### 6. Docker Engine

The core Docker application that builds and runs containers using Docker components and services.

### 7. Docker Hub

A cloud-based registry service for sharing and managing container images.

## 🛠️ Basic Commands

```bash
# Check Docker version
docker --version

# Pull an image from Docker Hub
docker pull nginx

# Run a container
docker run -d -p 8080:80 nginx

# List running containers
docker ps

# Stop a container
docker stop <container_id>

# Remove a container
docker rm <container_id>

# Build an image from a Dockerfile
docker build -t myapp .

# Run a container with a volume
docker run -v /host/path:/container/path myapp
```

## 📄 Sample Dockerfile

```Dockerfile
# Use official Python image
FROM python:3.10

# Set working directory
WORKDIR /app

# Copy files
COPY . .

# Install dependencies
RUN pip install -r requirements.txt

# Run the app
CMD ["python", "app.py"]
```

##  Dockerfile

```
# Use an official Python runtime as a parent image
FROM python:3.8-slim

# Set the working directory
WORKDIR /app

# Copy the current directory contents into the container
COPY . /app

# Install any needed packages
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]
```

### 📦 Images

```
# Pull an image from Docker Hub
docker pull <image_name>

# List downloaded images
docker images

# Remove an image
docker rmi <image_name>

# Build an image from a Dockerfile
docker build -t <image_name> .
```

### 🐳 Containers

```
# Run a container from an image
docker run <image_name>

# Run a container in detached mode
docker run -d <image_name>

# List running containers
docker ps

# List all containers (including stopped ones)
docker ps -a

# Stop a container
docker stop <container_id>

# Start a stopped container
docker start <container_id>

# Remove a container
docker rm <container_id>

# Execute a command in a running container
docker exec -it <container_id> <command>

# View container logs
docker logs <container_id>
```

### Docker Compose

```
# Start services defined in docker-compose.yml
docker-compose up

# Start services in detached mode
docker-compose up -d

# Stop and remove containers, networks
docker-compose down

# View running services
docker-compose ps
```

### 📂 Volumes

```
docker volume create my_volume
docker run -v my_volume:/data my-image
```

### 🌐 Networks

```
docker network create my_network
docker run --network=my_network my-image
```

### 🛠️ Debugging

```
docker logs my-container
docker exec -it my-container bash
```

------

## 🧩 Example: Run PostgreSQL in Docker

```
docker run -d \
  --name postgres-db \
  -e POSTGRES_USER=admin \
  -e POSTGRES_PASSWORD=secret \
  -e POSTGRES_DB=testdb \
  -p 5432:5432 \
  postgres:14
```

Now you can connect with:

```
psql -h localhost -U admin -d testdb
```

------

## 🎯 Key Takeaways

- **Images** = blueprints, **Containers** = running instances.
- **Dockerfile** defines how images are built.
- **Volumes** and **Networks** make Docker useful for real data engineering pipelines.
- Always use `docker-compose` for multi-container workflows (e.g., Airflow + Postgres).



## 🧪 Try It Yourself

1. Install Docker from [docker.com](https://www.docker.com/)
2. Create a simple app (e.g., Python or Node.js)
3. Write a Dockerfile
4. Build and run your container

