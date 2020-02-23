# ToC <a name='Top'></a>
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
  - Components
    - Docker Daemon (Server)
    - Docker Client
  - Roles
    - Docker File: A template (java class definition)
    - Docker Image: A template (compiled class file)
    - Docker Container: An object 
    - 
[Top](#top)
# Docker hub <a name='hub'></a>
  - The [Docker hub](https://hub.docker.com/search?q=&type=image) hosts pre-built images that you can [pull](#pull) and try without needing to define and configure your own.
[Top](#top)
# Docker CLI <a name='cli'></a>
[Top](#top)
# Commands
## pull <a name='pull'></a>
- docker pull
[Top](#top)
## Build docker image from dockerfile <a name='build'></a>
docker build -t image_name:image_tag .
[Top](#top)
## Remover docker image <a name='rmi'></a>
docker rmi image_id
[Top](#top)
## start a new container from image (id) <a name='run'></a>
docker run --name container_name -i -t img_id /bin/bash
[Top](#top)
### run docker as nvidia docker
docker run --name container_name --runtime=nvidia -v /path/on/host:/path/on/docker -i -t image_id /bin/bash
[Top](#top)
### exporting port to host
docker run --name container_name --runtime=nvidia -p 0.0.0.0:6060:6060 -v /path/on/host:/path/on/docker -i -t image_id /bin/bash
[Top](#top)
## stop a container <a name='stop'></a>
docker stop container_id
[Top](#top)
## remove a container <a name='rm'></a>
docker rm container_id
[Top](#top)
## create an image from container
docker commit container_id a_name_for_the_image
docker commit image_id containe_name
[Top](#top)
## list of containers <a name='ps'></a>
docker ps
[Top](#top)
## list of images
docker images
[Top](#top)
## run a container <a name='exec'></a>
docker exec -ti container_id /bin/bash
[Top](#top)
## link host's folder (/media/data) to docker-image (/root/sharedfolder)
nvidia-docker run --ipc=host -it -d -v /path/on/host:/path/on/docker container_id bash
docker run --name place_container1 -t -d -v /path/on/host:/path/on/docker
[Top](#top)
## exit docker environment
Ctrl P , Ctrl Q
[Top](#top)
