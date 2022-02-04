# Dockerfile: Ubuntu-node
Now we are going to show how to create an image with a dockerfile using ubuntu distribution, installing node js, npm and executing a javascript command.

```sh
# Dockerfile content
FROM ubuntu:latest

COPY message.js /tmp/message.js

RUN apt-get update && \
	apt-get install -y nodejs && \
	apt-get install -y npm

CMD ["node", "/tmp/message.js"]
```

First of all we have to build the image:
```sh
# docker build 
docker build -t ubuntu-node .
```

Second execute the docker image:
```sh
docker run -it ubuntu-node

#output
My first Ubuntu docker image with node.js
```

Third we can get into the image and see if node is installed and the version
```sh
docker run -it ubuntu-node /bin/ash
node -v
```