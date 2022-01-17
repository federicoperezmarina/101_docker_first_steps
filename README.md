# 101_docker_first_steps
This is an small workshop to start using docker (first steps)

## Table of Contents

* [Docker Cheat Sheet](#docker_cheat_sheet)
* [Docker Version](#docker_version)
* [Docker First Run](#docker_first_run)

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