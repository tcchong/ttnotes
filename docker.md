# Docker
> Docker is an open platform for developers and sysadmins to build, ship, and run distributed applications, whether on laptops, data center VMs, or the cloud.
>
> https://www.docker.com/

### docker commands

```
# login to shell
$ docker exec -it <CONTAINER_ID_OR_NAME> /bin/bash

# login with root
$ docker exec -it -u root <CONTAINER_ID_OR_NAME> /bin/bash

# commit
$ docker commit <CONTAINER_ID> <NAME>

# remove untagged images
$ docker rmi $(docker images -q --filter "dangling=true")
```

### docker-compose
> Compose is a tool for defining and running multi-container Docker applications. 
>
> https://docs.docker.com/compose/overview/

```
# Configure your docker-compose.yml
$ touch docker-compose.yml

# Build with Dockerfile
$ docker-compose build

# Run service
$ docker-compose up

# Run service in the background (detached mode)
$ docker-compose up -d <APP>

# Run service with updated images
$ docker-compose up --no-deps -d <APP>
```

`Sample docker-compose.yml with Node.js`

```
# docker-compose.yml
yourapp:
  build: .
  ports:
    - "3000:3000"
```

### docker-machine
> Docker Machine is a tool that lets you install Docker Engine on virtual hosts, and manage the hosts withdocker-machine commands.
>
> https://docs.docker.com/machine/overview/



### docker-swarm





# Reference
- http://blog.jez.io/2015/07/12/docker-tips-and-cheatsheet/
