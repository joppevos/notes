### add mount to directory
run -v /to/directory:


### stop all containers:
docker kill $(docker ps -q)

### remove all containers
docker rm $(docker ps -a -q)

### remove all docker images
docker rmi $(docker images -q)

### run container that closes and deletes after exit
docker run --rm

### run container with TTY
docker run --it

### make nvidea-docker run
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list

sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker
