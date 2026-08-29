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
