# Docker

## Definition

- Docker is a container technology, a tool for creating and managing containers
- Container is a package of code and dependencies to run that code (Ex: NodeJS code + NodeJS runtime)
- Why we use docker:
  - To have the exact same environment for development and production
  - Share development environment
  - Don't have to install/uninstall when change dependencies version

## CMD Docker

- docker run -d --name=`name` `image`: run image with name in background
- docker run -p `NodePort`:`port` `image`: run image in port
- docker run --link `host name`:`container name`: link host container to other container by container name
