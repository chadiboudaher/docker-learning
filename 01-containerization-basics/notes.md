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
