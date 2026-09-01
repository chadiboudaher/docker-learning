# Docker Basic commands

## Check version

```bash
docker info
docker version
docker -v
```

These command are written in the order of output size outputted atfer execution.

## docker pull

```bash
docker pull [OPTIONS] IMAGE[:TAG]
```

TAG: for the version, if none then then the latest is given.
OPTIONS:

- `docker pull --all-tags`: used to pull all versions of the image

## docker images

List the available Docker images on the local Docker host

```bash
docker images [OPTIONS]
```

- `docker images -q`: list all the available **image IDs**

## dokcer ps

List the running containers on the Docker host.

```bash
docker ps [OPTIONS]
```

- `docker ps -a (or -all)`: All the containers, the stopped and running ones.

## docker create

Create a container in a stopped state (does not start it)

```bash
docker create [OPTIONS] IMAGE [COMMAND] [ARG]
```

- `docker create --name my-container nginx`: Create a container where its name is my-container and image is nginx.
- `docker create --name my-container ubuntu:20.04`: Create a container where its name is my-container and image is ubuntu release 20.04.

## docker start

Start an already container that is not running

```bash
docker start [OPTIONS] CONTAINER [CONTAINER]
```

- `docker start abc1234`: Start the specific container (by id).
- `docker start container1 container2`: Start multiple containers.

## docker stop

Stop a running Docker container gracefully. If the process doesn't terminate within a certain timeout period (by default 10 seconds)

```bash
docker stop [OPTIONS] CONTAINER [CONTAINER]
```

- `docker stop my-container`: Stop the container my-container
- `docker stop -t 30 my-container`: Stop the container my-container and allow it 30 seconds to stop gracefully.
- `docker stop container1 container2`: Stop the two specific containers.

## A Container is a Software Process

```bash
ps [OPTIONS]
```

- `ps a`: Show processes for all users (not just yours).
- `ps -A`: Show all processes.
- `ps x`: Show processes not attached to a terminal.
- `ps u`: Show process owner (user) and display in user-friendly format.

## docker exec

Used to execute a command inside **a running** Docker container.

- It can be used to interact with a container's file system, processes, and environment.

```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG]
```

- `docker exec my-container ls usr/src/app`: Run the **ls** command inside the container my-container to list the contents of the /usr/src/app directory.

## docker exec: -t Option

```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG]
```

- `docker exec -t my-container ls /app`

## docker exec: -i Option

```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG]
```

- `docker exec -i my-container cat /etc/hostname`: (-i or -interactive), it keeps the container through the standart input. Use it with interactive commands that expect user input like vim, bash, sh or applications that require input.

## docker exec -it: Opening a Terminal Inside the Container

- `docker exec -it my-container /bin/bash`: The two flags (-i or -t) are often used together to bind the I/O streams of the container to s pseudo terminal, creating an interactive terminal session.

## docker run

Create and start a container from a specified image in a single step.

```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG]
```

- `docker run nginx`: create and start a container using latest nginx image.
- `docker run --name cont1 ubuntu:20.04`: Create and start a container from ubuntu:20.04 image and assign it a name cont1
- `docker run -d nginx`: Create and start container from image nginx in the background (-d detached mode).

## docker run -it Options

- `docker run -it ubuntu /bin/bash`

## docker run -rm Options

Create and run an ubuntu container, echo the sentence "This will self-destruct", then delete the container

- Use it for one off containers such testing
- Do not use for long term containers

```bash
docker run --rm ubuntu echo "This will self-destruct"
```

## docker inspect

Use to retrieve detailed, low-level information about **containers**, **images**, **volumes**, or networks in JSON format.

- You can run docker inspect on both running and stopped containers.

```bash
docker inspect [OPTIONS] OBJECT [OBJECT]
```

- `docker inspect my-container`: Returns detailed information about the container (name, ID, Network, COnfig...)
- `docker inspect nginx:latest`: Returns information about the image named nginx with the latest tag, including: Image ID, Creation time and more
