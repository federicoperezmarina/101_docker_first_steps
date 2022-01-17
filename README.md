# 101_docker_first_steps
This is an small workshop to start using docker (first steps)

## Table of Contents

* [Docker Cheat Sheet](#docker_cheat_sheet)
* [Docker Version](#docker_version)
* [Docker First Run](#docker_first_run)
* [Docker Getting Started](#docker_getting_started)
* [Docker Search](#docker_search)

## Docker Cheat Sheet
We have an small pdf docker-cheat-sheet.pdf which contains some useful commands to start using docker

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