# Docker
> Docker is an open platform for developers and sysadmins to build, ship, and run distributed applications, whether on laptops, data center VMs, or the cloud.
>
> https://www.docker.com/

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
$ docker-compose up -d
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