1. Download docker-deploy-hdp30.sh from Hortonworks
  - root@SPIMELAB:/home/uzair/Downloads/HDP_3.0.1# sh docker-deploy-hdp30.sh
  - Above script download sandbox-hdp container image
```shell
  REPOSITORY                  TAG                 IMAGE ID            CREATED             SIZE
hello-world                 latest              fce289e99eb9        13 months ago       1.84kB
hortonworks/sandbox-hdp     3.0.1               ae1d1779b081        14 months ago       27.5GB
hortonworks/sandbox-proxy   1.0                 38addccc7261        20 months ago       109MB
```
2. Create a container
```shell 
root@SPIMELAB: docker run -d -it --privileged --name=hdp3.0_privileged ae1d1779b081 /usr/sbin/init
```
and 
```shell 
root@SPIMELAB: docker run -d -it --privileged --name=hdp3.0_proxy1 38addccc7261
```
3. Launch the hdp3.0_privileged container
```shell
docker exec -it hdp3.0_privileged /bin/bash
```
4. Check status
```shell
root@SPIMELAB:/# docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                        NAMES
be161e7b70f8        38addccc7261        "nginx -g 'daemon of…"   3 minutes ago       Up 3 minutes        80/tcp                       hdp3.0_proxy1
664250b59903        ae1d1779b081        "/usr/sbin/init"         23 minutes ago      Up 23 minutes       22/tcp, 4200/tcp, 8080/tcp   hdp3.0_privi
```
5. Docker start/stop
```shell
docker stop hdp3.0
docker start hdp3.0
docker rm hdp3.0
```
6. Remove image
```shell
docker rmi hortonworks/sandbox-hdp:{release}
```
[More Info](#https://www.cloudera.com/tutorials/sandbox-deployment-and-install-guide/3.html#memory-for-linux)
