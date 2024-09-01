### Interact with container

`docker exec -it <containerId> /bin/bash`

### Run Image

`docker run -p 27017:27017 -d mongo`

### Create volume

`docker run -v volume_database:/data/db -p 27017:27017 mongo`

### Kill container

`docker kill <containerId>`
