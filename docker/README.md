# Docker

## Definition

- Docker is a container technology, a tool for creating and managing containers
- Image is a package of code and dependencies to run that code (Ex: NodeJS code + NodeJS runtime)
- Container is the running image (Execute the code)
- Why we use docker:
  - To have the exact same environment for development and production
  - Share development environment
  - Don't have to install/uninstall when change dependencies version

## CMD Docker

- docker ps: get list of running containers
- docker ps -a: get list of existing containers

- docker run -d --name=`name` `image`: run image with name in background
- docker run -p `local port`:`docker port` `container name`: run image in port
- docker run --link `host name`:`container name`: link host container to other container by container name

- docker build `Dockerfile path`:build an image from the Dockerfile

- docker stop `container name`: stop a running container
- 