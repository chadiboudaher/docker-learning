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
