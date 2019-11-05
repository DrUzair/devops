## Build docker image from dockerfile
docker build -t dockerfile .
## Remover docker image
docker rmi image_id

## start a new container from image (id)
docker run --name container_name -i -t img_id /bin/bash
## run docker as nvidia docker
docker run --name container_name --runtime=nvidia -v /path/on/host:/path/on/docker -i -t image_id /bin/bash

## exporting port to host
docker run --name container_name --runtime=nvidia -p 0.0.0.0:6060:6060 -v /path/on/host:/path/on/docker -i -t image_id /bin/bash

## stop a container
docker stop container_id

## remove a container
docker rm container_id

## create an image from container
docker commit container_id a_name_for_the_image
docker commit image_id containe_name

## list of containers
docker ps

## list of images
docker images

## run a container
docker exec -ti container_id /bin/bash

## link host's folder (/media/data) to docker-image (/root/sharedfolder)
nvidia-docker run --ipc=host -it -d -v /path/on/host:/path/on/docker container_id bash
docker run --name place_container1 -t -d -v /path/on/host:/path/on/docker

## exit docker environment
Ctrl P , Ctrl Q
