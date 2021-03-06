#Workshop 1: Install Docker

## 1. Download and install
- Windows 10: [Docker Community Edition for Windows](https://store.docker.com/editions/community/docker-ce-desktop-windows). 
- Mac OSX: [Docker Community Edition for Mac](https://store.docker.com/editions/community/docker-ce-desktop-mac)  
- Ubuntu: [Docker Community Edition for Ubuntu](https://store.docker.com/editions/community/docker-ce-server-ubuntu)
	
## 2. Check docker functional
After finished then run below command for check docker fuctional

```
docker run hello-world
```

Expect Result

```
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://cloud.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/engine/userguide/
```

## 3. Pull images
Run command below for pull image and preparation (Line-by-Line): This will take about 15 - 20 min for pull

```
docker pull bitnami/nginx
docker pull bitnami/php-fpm
docker pull bitnami/postgresql
docker pull composer
```

## 4. Basic Commands
ref from [docker-tutorial-series](https://rominirani.com/docker-tutorial-series-part-2-basic-commands-baaf70807fd3)

```
docker version
docker info
docker images #check sizing and detail of all image
docker inspect bitnami/nginx:latest
docker search nginx
docker ps --all 

```
### 4.1 try to run and ssh to container immediately

```
docker run -t -i busybox
ls -l
exit
```

## 5. Run Container from Image
### 5.1. run docker for nginx web server by command

```
docker run -dt --user root --name nginxtest -p 80:8080 -p 443:8443 bitnami/nginx
```

### 5.2. open browser with url: 

```
http://localhost
https://localhost
```

### 5.3. access shell to container with command:

```
docker exec -it nginxtest bash
```

### 5.4. Check file ```index.html``` with command: 

```
more index.html
```

### 5.5. Check current path inside container by command: 

```
pwd
exit
```
### 5.6. Stop container and remove running container by command:

```
docker ps
docker stop nginxtest
docker ps
docker ps -a
docker rm nginxtest
```

### 5.7. Remove Images by command:

```
docker images
docker rmi bitnami/nginx
```

### 5.8. Remove all unnecessary process and images to cleanup workshop

```
use command that your learned above
``` 
