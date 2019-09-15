### stop all containers:
docker kill $(docker ps -q)

### remove all containers
docker rm $(docker ps -a -q)

### remove all docker images
docker rmi $(docker images -q)

### run container that closes and deletes after exit
docker run --rm

### run container with TTY
docker run -it

### view the layers an image is build off
docker history <image>

### remove docker images that are unsued
docker image prune -f

### make nvidea-docker run
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list

sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker

### add gpu to docker container
docker run --gpus all

### add hosts current folder location to docker container DOES NOT COPY
docker run -v`pwd`:/folder_name

## DOCKERIMAGE
### Copy the content of current directory into the container 
WORKDIR /app
COPY . /app




