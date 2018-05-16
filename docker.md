
* Docker containers are a means to package applications and their dependencies in a standardized way.
* A Docker host is the container runtime which hosts containers and might run on the same machine as the Docker CLI,
or it might run on a remote server, on-premise or in the cloud.

* Each line of a Dockerfile results in a layer in the resulting image.
* Only the WORKDIR keyword sets the context across the layers of the image.


* inspect an IMAGE
`docker image inspect <image>`

* inspect a CONTAINER
`docker container inspect <container>`

* Debugging and cleanup
```
docker version
docker system info
docker system df -v
docker system events

docker container prune
docker image prune
docker volume prune
docker network prune
docker systemprune
```
