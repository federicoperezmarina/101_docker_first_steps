# Dockerfile: Alpine-node
Now we are going to show how to create an image with a dockerfile using alpine distribution, installing node js, npm and executing a javascript command.

```sh
# Dockerfile content
FROM alpine:latest

COPY message.js /tmp/message.js

RUN apk add --update nodejs npm

CMD ["node", "/tmp/message.js"]
```

First of all we have to build the image:
```sh
# docker build 
docker build -t alpine-node .
```

Second execute the docker image:
```sh
docker run -it alpine-node

#output
My first Alpine docker image with node.js
```

Third we can get into the image and see if the library requests is installed
```sh
docker run -it alpine-node /bin/ash
npm help
```