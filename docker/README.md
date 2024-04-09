# Docker

## Definition

- Docker is a container technology, a tool for creating and managing containers
- Container is the running image (Execute the code)
- Why we use docker:
  - To have the exact same environment for development and production
  - Share development environment
  - Don't have to install/uninstall when change dependencies version

## Image

- Image is a package of code and dependencies to run that code (Ex: NodeJS code + NodeJS runtime)
- Images are read-only. Every changes you made to your project, docker image will not update => you need to build docker image every time you update your project
- Every instruction in an image creates a cacheable layer - layers help with image re-building and sharing.

## CMD Docker

- docker ps: get list of running containers
- docker ps -a: get list of existing containers

- docker run `image name`: run image in attach mode (listen to the logs of a container)
- docker run -d --name=`name` `image`: run image with name in detach mode (can't listen the logs of a container)
- docker run -p `local port`:`docker port` `image name`: run image in port
- docker run --link `host name`:`container name`: link host container to other container by container name
- docker run -it `image name`: run image in attach mode and you can interact with the container
- docker run -rm `image id`: run image and auto delete container after container stop
- docker run --name `container name` `image name`: run a container from a image with name   
  
- docker start `container name/container id`: restart a stopped container in detach mode
- docker start -a `container name/container id`: restart a stopped container in attach mode
- docker start -a -i `container name/container id`: restart a stopped container in attach mode and you can interact with the container

- docker build `Dockerfile path`: build an image from the Dockerfile
- docker build -t `image name`:`image version` `Dockerfile path`: build an image from the Dockerfile with name and tag version

- docker stop `container name`: stop a running container
- docker rm `container name`: remove container

- docker attach `container name`: attach to a running container

- docker logs `container name`: see all the logs inside a container
- docker logs -f `container name`: attach to a running container

- docker images: get list of images
- docker rmi `image id`: remove image by id and all its layer
- docker image inspect `image id`: view image detail

- docker cp `file path local system` `container name`:/`file path inside container`: copy folder from local machine to docker
- docker cp `container name`:/`file path inside container` `file path local system`: copy folder from container to local machine
