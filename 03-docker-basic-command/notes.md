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
