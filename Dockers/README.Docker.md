# Dockers

## 1) Basics ( layers , volume)

### Create build

`docker build -t <repository_name>:<tag_name> .`

### check logos

`docker ps`
`docker logs <container_id>`

### Interact with container

`docker exec -it <container_id> /bin/bash`

### Run Image

`docker run -p 27017:27017 -d mongo`

### Create volume

`docker run -v volume_database:/data/db -p 27017:27017 mongo`

### Kill container

`docker kill <container_id>`

### Remove images (force if necessary)

`docker rmi <image_name> --force`

## 2) Network

### Create network

`docker network create <network_name>`

-- > build image

### Connect two containers in a network

_MONGOURL : 'mongodb://volumeName:27017/dbname_

- Connect volume with mongo in a network

`docker run -d -v <volume_folder>:/data/db --name <volume_name> --network <network_name> -p 27017:27017 mongo`

- Connect backend with mongoImage in a network

`docker run -d -p 3000:3000 --name <backend_name> --newtork <network_name> <image_tag_name>`

## 3) Docker Push

`docker push <username>/<image_name>:<tag_name>`

## 4) Docker compose

Run the yaml file : `docker-compose up`

backend:
build: . (for building image by container itself by docker-compose up)
image: "backend" (for user to build image then run docker-compose up)

## 5) Bind Mount

`docker run -p 3000:3000 -v ./app:/<project_name>/app  <image_name>`

## 6) Edit folder inside cotainer

`docker exec -it <contianer_id> /bin/bash`

`apt-get update`

`apt-get  install vim`
