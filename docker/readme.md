# ToC
- Story(#story)
- [Docker hub](#hub)
- CLI (#cli)
- Commands
  - [pull](#pull)
  - [build](#build)
  - [rmi](#rmi)
  - [run](#run)
  - [stop](#stop)
  - [rm](#rm)
  - [ps](#ps)
  - [exec](#exec)
  
# Docker Story <a name='story'></a>
  - Actors
    - Docker Daemon (Server)
    - Docker Client
# Docker hub <a name='hub'></a>
  - The [Docker hub](https://hub.docker.com/search?q=&type=image) hosts pre-built images that you can [pull](#pull) and try without needing to define and configure your own.

# Docker CLI <a name='cli'></a>

# Commands
## pull <a name='pull'></a>
- docker pull
## Build docker image from dockerfile <a name='build'></a>
docker build -t image_name:image_tag .
## Remover docker image <a name='rmi'></a>
docker rmi image_id

## start a new container from image (id) <a name='run'></a>
docker run --name container_name -i -t img_id /bin/bash
### run docker as nvidia docker
docker run --name container_name --runtime=nvidia -v /path/on/host:/path/on/docker -i -t image_id /bin/bash

### exporting port to host
docker run --name container_name --runtime=nvidia -p 0.0.0.0:6060:6060 -v /path/on/host:/path/on/docker -i -t image_id /bin/bash

## stop a container <a name='stop'></a>
docker stop container_id

## remove a container <a name='rm'></a>
docker rm container_id

## create an image from container
docker commit container_id a_name_for_the_image
docker commit image_id containe_name

## list of containers <a name='ps'></a>
docker ps

## list of images
docker images

## run a container <a name='exec'></a>
docker exec -ti container_id /bin/bash

## link host's folder (/media/data) to docker-image (/root/sharedfolder)
nvidia-docker run --ipc=host -it -d -v /path/on/host:/path/on/docker container_id bash
docker run --name place_container1 -t -d -v /path/on/host:/path/on/docker

## exit docker environment
Ctrl P , Ctrl Q
