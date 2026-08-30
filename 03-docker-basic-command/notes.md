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
