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
