
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

Patterns for dealing with the complexity of a distributed application

* Loosely coupled components
* Minimizing stateful components and preferring stateless components whenever possible
* Service discovery (via an external authority such as DNS)
* Routing at various layers in OSI model
* Load balancing (common round robin)
* Defensive programming (against services dependent upon)
* Retries (exponential backoff)
* Logging (aggregate logs using service)
* Error handling (fail fast)
* Redundancy
* Health checks (auto-healing)
* Circuit breaker pattern

Rolling out irreversible data changes using 3-step process:

1. Roll out a backward-compatible schema and data change
2. If successful, roll out new code
3. If successful, clean up schema and remove backward-compatibility


### Single-Host Networking

```
docker network ls
docker network inspect bridge
```


### Orchestrators

Tasks of an Orchestrator

* Reconciling the desired state
* Replicated (n number of services) and global services (1 service per worker node in cluster)
  (In Kubernetes, a global service is also called a daemon set)
* Service discovery
* Routing (same node in cluster, different node in cluster, outside of cluster)
* Load balancing
* Scaling
* Self-healing
* Zero downtime deployments
* Affinity and location awareness
* Security
  - Secure communication and cryptographic node identity
  - Secure networks and network policies
  - Role-based access control
  - Secrets
  - Content trust
  - Reverse uptime
* Introspection

### No Deps

```
docker-compose run --rm --no-deps foo_service rake db:reset
```
