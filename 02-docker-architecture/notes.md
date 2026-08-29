# Docker Architecture

## Containers Overview

A container is a lightweight, isolated process running on a shared operating system kernel, packaged with everything it needs to run, including code, libraries, environment variables, runtime, configuration files.

- We can run applications inside containers.

### Containers - Features

- Does not require a seperate OS
- isolated, self-contained environments
- Faster to create, start, and tear down
- Repeatable
- Portable
- Easily scalable

### Containerization Overview

To build, ship and run containers, we need a container runtime engine installed on the host's operating system

- Containerized applications are "isolated"

### Docker Containers - From a Dockerfile to an Application

Starting with a Dockerfile, we can build a container image that can be used to consistently run an application across different environments.

Can we run containers on Virtual Machines.

### Virtual Machines (VMs) vs. Containers (cont.)

| Virtual machines             | Containers                         |
| ---------------------------- | ---------------------------------- |
| Heavyweight (slow to start)  | Lightweight (start in ms)          |
| Limited Scalability          | Faster Scaling                     |
| Low Portability              | Excellent portability              |
| Redundamt OS overhead        | share the host OS kernel           |
| Inefficient Image Management | Efficient Image Management         |
| Poor Dev/Test/Prod parity    | Containers are excellent for CI/CD |

## Docker Architecture

Docker is a software platform that simplifies the process of building, running, managing, and distributing applications using containers.

### Docker Client

- it enables developers/users to interact with Docker.
- When you use docker command, the docker client sends these commands to the Docker daemon (dockerd)

### Docker Host

The server or virtual machine on which Docker Engine is installed

- The Docker Daemon (dockerd) is the heart of Docker

### Docker Images

images are read-only binary templates used to build containers.

- They contain the application code, libraries, and dependencies required to run an application

### Docker Daemon

- It listens to Docker API requests and manages containers, images, network, and volumes.
- It builds container images as requested by the client
- It interfaces with docker registries to pull or publish images as requested by the client.

### Docker Containers

Containers and encapsulated environments in which you run applications.

### Docker Registries

- A Docker registry stores Docker images
- Docker Hub is the public registry that anyone can use

### Understanding How Docker Works

**Docker CLI**

- Docker CLI communicates with the Docker Daemon/server, dockerd

**dockerd**

- dockerd processes the docker API requests and utilizes containerd functionality to manage the container's life-cycle.

**Containerd**

- Manages containers, Storage, and Networking
- Pushes and pulls images

**runC**

- Created and runs containers
