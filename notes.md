
# command to kill all docker processes
docker container rm -f $(docker container ls -aq)

#recalaim disk space
docker image rm -f $(docker image ls -f reference='diamol/*' -q

#run a docker container
docker container run diamol/ch02-hello-diamol)

#Run a docker container and connect to it like a remote computer
docker container run --interactive --tty diamol/base

#list running dockers
docker container top <container_id>

#logs of container
docker container logs <container_id>

#inspect container
docker container inspect <container_id>

#list all containers
docker container ls --all

#Runninp a website using docker
docker container run --detach --publish 8080:80 diamol/ch02-hello-diamol-web

#Pulling a docker image
docker image pull diamol/ch03-web-ping

#Running ch03-web-ping container
docker container run -d --name web-ping diamol/ch03-web-ping

#Running  ch03-web-ping container with customized envirionment variable (TARGET)
docker container run --env TARGET=google.com diamol/ch03-web-ping
docker container run -e TARGET=docker.com -e INTERVAL=5000 web-ping

#Building a docker image
cd ch03/exercises/web-ping
docker image build --tag web-ping .

#list docker images
docker image ls 'w*'

#image history
docker image history web-ping

#Docker image size
docker system df
