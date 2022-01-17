# 101_docker_first_steps
This is an small workshop to start using docker (first steps)

## Table of Contents

* [Docker Cheat Sheet](#docker-cheat-sheet)
* [Docker Version](#docker-version)
* [Docker First Run](#docker-first-run)
* [Docker Getting Started](#docker-getting-started)
* [Docker Search](#docker-search)
* [Docker Images](#docker-images)
* [Docker ps](#docker-ps)
* [Docker help](#docker-help)
* [Docker containers](#docker-containers)
* [Docker rm](#docker-rm)
* [Docker run bash](#docker-run-bash)
* [Docker build](#docker-build)

## Docker Cheat Sheet
We have an small pdf [docker-cheat-sheet.pdf](https://github.com/federicoperezmarina/101_docker_first_steps/blob/main/docker-cheat-sheet.pdf) which contains some useful commands to start using docker

## Docker Version
Run "docker --version" permits us to obtain the version of docker that we have installed. 
```console
# Display the version of docker installed:
docker --version

# You will see a message like this
Docker version 20.10.10, build b485636 
```

## Docker First Run
Now we are going to do the first run of docker. We will pull, create and run the image 'hello-world'

```sh
#Pull, create, and run 'hello-world'
docker run hello-world
```

You will see an output in the sh/console like:
```console
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete 
Digest: sha256:975f4b14f326b05db86e16de00144f9c12257553bba9484fed41f9b6f2257800
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
 ```

 ## Docker Getting Started
 Now we are going to view the official getting started tutorial of docker

 ```sh
 docker run -d -p 80:80 docker/getting-started
 ```

 At this time we are able to go to the url "http://localhost/tutorial/" and view the tutorial in our browser
 ```
 http://localhost/tutorial/
 ``` 

 ## Docker Search
 Docker search is a command to find an image in the docker image repository

```sh
docker search nginx
```

Typing the command you will recibe the name of images with the search, a little description, the starts of the image and official flag
```console
NAME                              DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
nginx                             Official build of Nginx.                        16141     [OK]       
jwilder/nginx-proxy               Automated Nginx reverse proxy for docker con…   2109                 [OK]
richarvey/nginx-php-fpm           Container running Nginx + PHP-FPM capable of…   820                  [OK]
jc21/nginx-proxy-manager          Docker container for managing Nginx proxy ho…   312                  
linuxserver/nginx                 An Nginx container, brought to you by LinuxS…   160                  
tiangolo/nginx-rtmp               Docker image with Nginx using the nginx-rtmp…   151                  [OK]
jlesage/nginx-proxy-manager       Docker container for Nginx Proxy Manager        150                  [OK]
alfg/nginx-rtmp                   NGINX, nginx-rtmp-module and FFmpeg from sou…   114                  [OK]
nginxdemos/hello                  NGINX webserver that serves a simple page co…   82                   [OK]
privatebin/nginx-fpm-alpine       PrivateBin running on an Nginx, php-fpm & Al…   61                   [OK]
nginx/nginx-ingress               NGINX and  NGINX Plus Ingress Controllers fo…   59                   
nginxinc/nginx-unprivileged       Unprivileged NGINX Dockerfiles                  57                   
nginxproxy/nginx-proxy            Automated Nginx reverse proxy for docker con…   34                   
staticfloat/nginx-certbot         Opinionated setup for automatic TLS certs lo…   25                   [OK]
nginx/nginx-prometheus-exporter   NGINX Prometheus Exporter for NGINX and NGIN…   23                   
schmunk42/nginx-redirect          A very simple container to redirect HTTP tra…   19                   [OK]
centos/nginx-112-centos7          Platform for running nginx 1.12 or building …   16                   
centos/nginx-18-centos7           Platform for running nginx 1.8 or building n…   13                   
flashspys/nginx-static            Super Lightweight Nginx Image                   12                   [OK]
bitwarden/nginx                   The Bitwarden nginx web server acting as a r…   12                   
mailu/nginx                       Mailu nginx frontend                            10                   [OK]
webdevops/nginx                   Nginx container                                 9                    [OK]
sophos/nginx-vts-exporter         Simple server that scrapes Nginx vts stats a…   7                    [OK]
ansibleplaybookbundle/nginx-apb   An APB to deploy NGINX                          3                    [OK]
wodby/nginx                       Generic nginx                                   1                    [OK]
```

Now we can try it with some searches
```sh
docker search ubuntu
docker search alpine
docker search java
docker search angular
docker search mongodb
docker search elastic
docker search grafana
```

## Docker Images
The command "docker images" obtains the list of images that we have in our machine. Let's try it!

```sh
docker images
```

We will recieve an ouput like this:
```console
REPOSITORY                                      TAG            IMAGE ID       CREATED         SIZE
nmap                                            latest         64da15eba121   2 weeks ago     531MB
nginx                                           latest         f6987c8d6ed5   3 weeks ago     141MB
checkmk/check-mk-raw                            2.0.0-latest   953b035c79be   5 weeks ago     1.03GB
grafana/grafana                                 latest         3b1fc05e7c9a   5 weeks ago     275MB
influxdb                                        latest         07a3e66c579f   6 weeks ago     346MB
docker/getting-started                          latest         26d80cd96d69   6 weeks ago     28.5MB
grafana/loki                                    latest         e3e722f23de3   2 months ago    62.5MB
grafana/promtail                                latest         592b97aee96d   2 months ago    179MB
prom/prometheus                                 latest         c10e9cbf22cd   2 months ago    194MB
ubuntu                                          latest         ba6acccedd29   3 months ago    72.8MB
hello-world                                     latest         feb5d9fea6a5   3 months ago    13.3kB
grafana/grafana                                 7.3.7          13afb861111c   12 months ago   187MB
checkmk/check-mk-raw                            latest         3485c9125bc8   17 months ago   848MB
docker.elastic.co/logstash/logstash             7.7.0          30dcca1db5e9   20 months ago   740MB
docker.elastic.co/elasticsearch/elasticsearch   7.7.0          7ec4f35ab452   20 months ago   757MB
```

## Docker ps
The command "docker ps" is useful in order to know which images are up in our system. First of all we will have to start some image with docker.

```sh
docker run nginx
docker ps
```

We will recieve an ouput with the container_id, image, command, time of the run, status, ports and names
```console
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS     NAMES
d01c9ef54f35   nginx     "/docker-entrypoint.…"   3 minutes ago   Up 3 minutes   80/tcp    nifty_blackburn
```

## Docker help
We can run the command "docker help" in order to show the help of the docker

```sh
docker help
```

We will see the help of docker:
```console
Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Options:
      --config string      Location of client config files (default "/Users/03747930/.docker")
  -c, --context string     Name of the context to use to connect to the daemon (overrides DOCKER_HOST env var and default context set with
                           "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level ("debug"|"info"|"warn"|"error"|"fatal") (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default "/Users/03747930/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default "/Users/03747930/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default "/Users/03747930/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Management Commands:
  builder     Manage builds
  buildx*     Build with BuildKit (Docker Inc., v0.6.3)
  compose*    Docker Compose (Docker Inc., v2.1.1)
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  image       Manage images
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  scan*       Docker Scan (Docker Inc., 0.9.0)
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes

Run 'docker COMMAND --help' for more information on a command.

To get more help with docker, check out our guides at https://docs.docker.com/go/guides/
```

## Docker Containers
Containers are to Virtual Machines as threads are to processes.

### Lifecycle

* [`docker create`](https://docs.docker.com/engine/reference/commandline/create) creates a container but does not start it.
* [`docker rename`](https://docs.docker.com/engine/reference/commandline/rename/) allows the container to be renamed.
* [`docker run`](https://docs.docker.com/engine/reference/commandline/run) creates and starts a container in one operation.
* [`docker rm`](https://docs.docker.com/engine/reference/commandline/rm) deletes a container.
* [`docker update`](https://docs.docker.com/engine/reference/commandline/update/) updates a container's resource limits.

### Starting and Stopping

* [`docker start`](https://docs.docker.com/engine/reference/commandline/start) starts a container so it is running.
* [`docker stop`](https://docs.docker.com/engine/reference/commandline/stop) stops a running container.
* [`docker restart`](https://docs.docker.com/engine/reference/commandline/restart) stops and starts a container.
* [`docker pause`](https://docs.docker.com/engine/reference/commandline/pause/) pauses a running container, "freezing" it in place.
* [`docker unpause`](https://docs.docker.com/engine/reference/commandline/unpause/) will unpause a running container.
* [`docker wait`](https://docs.docker.com/engine/reference/commandline/wait) blocks until running container stops.
* [`docker kill`](https://docs.docker.com/engine/reference/commandline/kill) sends a SIGKILL to a running container.
* [`docker attach`](https://docs.docker.com/engine/reference/commandline/attach) will connect to a running container.

### Info

* [`docker ps`](https://docs.docker.com/engine/reference/commandline/ps) shows running containers.
* [`docker logs`](https://docs.docker.com/engine/reference/commandline/logs) gets logs from container.  (You can use a custom log driver, but logs is only available for `json-file` and `journald` in 1.10).
* [`docker inspect`](https://docs.docker.com/engine/reference/commandline/inspect) looks at all the info on a container (including IP address).
* [`docker events`](https://docs.docker.com/engine/reference/commandline/events) gets events from container.
* [`docker port`](https://docs.docker.com/engine/reference/commandline/port) shows public facing port of container.
* [`docker top`](https://docs.docker.com/engine/reference/commandline/top) shows running processes in container.
* [`docker stats`](https://docs.docker.com/engine/reference/commandline/stats) shows containers' resource usage statistics.
* [`docker diff`](https://docs.docker.com/engine/reference/commandline/diff) shows changed files in the container's FS.

### Import / Export

* [`docker cp`](https://docs.docker.com/engine/reference/commandline/cp) copies files or folders between a container and the local filesystem.
* [`docker export`](https://docs.docker.com/engine/reference/commandline/export) turns container filesystem into tarball archive stream to STDOUT.

### Executing Commands

* [`docker exec`](https://docs.docker.com/engine/reference/commandline/exec) to execute a command in container.

## Docker rm
Now we are going to remove a container. First of all we are going tu run a container, after we will stop & start & stop. Finally we will remove the container.

```sh
docker run nginx &
docker ps
docker stop <container_id>
docker ps
docker start <container_id>
docker ps
docker stop <container_id>
docker ps
docker rm <container_id>
```

## Docker run bash
We are going to run the image to go inside it and use some command inside the container.

```sh
docker run -it ubuntu /bin/bash
```

## Docker build
Now we are going to use the command "docker build". We need to use a Dockerfile. A dockerfile is simply a text-based script of instructions that is used to create a container image. Lets try it!

```sh
docker build -t getting-started-image .
```

After that we want tu run the image, we will use:
```sh
docker run -dp 3000:3000 getting-started-image
```