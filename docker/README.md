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

## Data

- Application (Code + Env):
  - Written and provided by you.
  - Cant be change once image is built.
  - Readonly and stored in Images
- Temporary Data (Ex: user input):
  - Created in running container.
  - Dynamic and changing.
  - Read + write, Temporary and stored in Container
- Permanent App Data (Ex: user account):
  - Created in running container.
  - Must not be lost
  - Read + write, Permanent and stored in Container and Volumes

## Volumes

- Are folders inside local machines which are mapped into containers
- Are managed by docker. Developer don't know where the folders are stored
- Container can read from volumes and write data into volumes
- Data inside volumes persist if a container shut down
- Type of volumes:
  - Anonymous volume: will be deleted by docker when container shut down
  - Named volume: will not be deleted by docker when container shut down
- Use for data that need to be persisted but developer don't need edit directly

## Bind Mounts

- Are similar to volumes but you can define a folder/path on local machine to be mapped into containers
- Use for data that need to be persisted but developer need edit directly (Ex: source code)

## CMD Docker

- docker ps: get list of running containers
- docker ps -a: get list of existing containers

- docker run `image name`: run image in attach mode (listen to the logs of a container)
- docker run -d --name `name` `image`: run image with name in detach mode (can't listen the logs of a container)
- docker run -p `local port`:`docker port` `image name`: run image in port
- docker run --link `host name`:`container name`: link host container to other container by container name
- docker run -it `image name`: run image in attach mode and you can interact with the container
- docker run --rm `image id`: run image and auto delete container after container stop
- docker run --name `container name` `image name`: run a container from a image with name
- docker run -v `volume name`:`volume path` `image name`: run a container from a image with a named volume
- docker run -v "`absolute path on your machine`:`volume path`" `image name`: run a container from a image with a bind mounts
- docker run -v `volume name`:`volume path` `image name`: run a container from a image with a named volume
- docker run -v `volume path` `image name`: run a container from a image with an anonymous volume
- docker run --env-file `path to env file` `image name`: run a container from a image using env file
- docker run --env `env name`=`env value` `image name`: run a container from a image using env
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

- docker volume ls: get list of volumes
- docker volume inspect `volume name`: get the detail of a volume
