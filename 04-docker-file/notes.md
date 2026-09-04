# Docker File

A Dockerfile is a text document that contains all the commands a user could use manually on the CLI to build an application.

Th command **docker build** reads the instructions in a docker file and creates a docker image.

```text
FROM ubuntu
MAINTAINER John Doe
RUN apt-get update
CMD ["echo", "Hello from DolfinED"]
```

## Docker File Structure - FROM

The FROM instruction wil set the base image for the Dockerfile

- Every Dockerfile instruction that follows FROM applies to this base image.

```bash
FROM <image>[:tag]
```

- `FROM ubuntu`: Pull the latest base Ubuntu image

## The Docker Layers

The docker image consists of layers. Basically each line has a layer, if we change a line, only that corresponding layer will change.

## Docker File Structure - RUN

RUN - runs one or more commands

- The RUN instruction will execute any commands ina new image layer and commit the results.

```bash
RUN <command>
```

## Inspecting Image Layers - docker history command

Use this command to display image layers and their details.

```bash
docker history <image name>
```

## Docker File Structure - CMD

CMD is used to specify the command to be executed when the container is started.

- Only one CMD instruction should exist in a Dockerfile.
- If there are more than one CMD instructions in a Dockerfile, only the last CMD instruction will take effect.
- CMD can be overridden at the container start time.

```bash
CMD ["executable", "param1", "param2"]
```

## docker build command explained

- PATH the build context - usually the current directory

```bash
dokcer build [OPTIONS] PATH | URL | -
```

- `docker build -t myapp.`: Build the image myapp from the dockerfile in the current directory. The current directory is the build context.

## Docker File Structure - EXPOSE

The EXPOSE instruction informs Docker that the container listens on the specified network ports at runtime.

- It is informational only

```bash
EXPOSE <port>
```
