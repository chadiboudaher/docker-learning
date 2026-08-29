# Containerization Basics

## Why Learn Docker?

- Docker is widely used in modern software development.
- It helps developers package applications consistently.
- It is commonly used in backend, AI, Ml projects, cloud, DevOps, and deployement workflows.
- Docker skills are valuable because many companies use containerized environments.

## Main Benefits of Docker

- **Environment Reproducibility**: Everyone gets the exact same setup (regardless of wether they are running it on a Mac, Windows, or Linux).
- **Dependency Management**: No python hell (multiple applications/tools requires different python versions), COnda weirdness, or OS-specific issues.
- **Portability**: Run your container on any machine with Docker (dev laptop, server, cloud instance).
- **Version Control for Environments**: Dockerfiles are text = versionable in Git.

## From Physical Servers to Virtualization

### Compute Device Components

1. **Central Processing Unit (The Brain)**: Is involved in all operations that run on the compute device.
2. **Random Access Memory (RAM)**: Used to run and hold data during processing.
3. **Hard Disk Drives (HDD) & Solid-State Drives (SSD)**: Used to provide persistent storage for OS, Data and Applications.
4. Network Interface Cards: Connect the computing device to the outside world. Can be wireless or wired (uses Ethernet/LAN cables).
5. **GCPUs**: Used to accelerate video operations (gaming, rendering) on the compute device. Can be built-in or a card.

### What is a Server?

A server is basically a powerful computing device with:

- A good size memory (RAM).
- One or more CPU(s)
- One or more disk drivers to persistently store the operating system, applications, and data.
- One or more network interfaces.
- One or more GCPUs.

#### Scaling Servers

As the number of users increases.

- The server performence may degrade.
- We need to increase (scale) the number of servers (with a logic and processes to follow).
- Which lead to building **Datacenters**.

#### Server Hosting in Datacenters

A data center is an air conditioned, secure, and monitored space.

#### Server Resources Optimization & Multiple Apps on a Server

To optimize resource usage, multiple applications could be run on the same physical server.

- Each application may require its own runtime version, dependencies, database, etc

Drawbacks:

- Resource contention and inefficiency.
- Dependency conflicts.
- Lack of strong isolation - Security Risks.
- Deployment & maintenance hell.
- Lack of portability.

## Introduction to Virtulization

Virtualization introduced isolation, flexibility, protability, and scalability. It enables us to run more than one virtual machine, multiple operating systems, and applications on a single physical server.

![Virtulization](https://github.com/chadiboudaher/docker-learning/blob/main/images/Virtualization.png)

### Core Architecture

1. **Physical Hardware (Host)**: The actual server containing CPU, RAM, storage, and network resources.
2. **Hypervisor**: Software that creates and manages Virtual Machines by allocating hardware resources to them.
3. **Virtual Machine (Guest)**: A software-based computer that runs its own Operating System, applications, and libraries independently of other VMs.

#### Virtual Machines (VMs) - Issues

- Heavyweight (slow to start)
- Limited Scalability
- Poor Dev/Test/Prod parity
- Redundant OS overhead
- Inefficient Image Management
- Low portability

## From Virtualization to containers - The background

### Linux Software Processes Overview

A process is a running instance of a program that has its own memory, CPU context, and system resources, managed by the linux kernel.

When you run a program (like bash, nginx, or python), the Linux kernel:

1. Loads the program's code into memory
2. Alloctes it a unique Process ID (PID)
3. Create a process to execute the code

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
