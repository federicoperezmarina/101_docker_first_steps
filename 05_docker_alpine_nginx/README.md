# Dockerfile: Alpine-nginx
Now we are going to show how to create an image with a dockerfile using alpine distribution, installing python and executing a python command.

```sh
# Dockerfile content
FROM alpine:latest

LABEL creator="federicoperezmarina@gmail.com"
LABEL version="1.0"
LABEL description="This is an alpine image with nginx"

RUN apk update && \
    apk add openrc && \
    mkdir /run/openrc && \
    touch /run/openrc/softlevel && \
    apk add nginx && \
    adduser -D -g 'www' www && \
    mkdir /www && \
    chown -R www:www /var/lib/nginx && \
    chown -R www:www /www && \
    mv /etc/nginx/nginx.conf /etc/nginx/nginx.conf.orig  

COPY index.html /www/
COPY nginx.conf /etc/nginx/    

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

First of all we have to build the image:
```sh
# docker build 
docker build -t alpine-nginx .
```

Second execute the docker image:
```sh
docker run -it -p 80:80 -d alpine-nginx:latest
```

Third we can get into the image and see if the library requests is installed
```sh
docker run -it alpine-nginx /bin/ash
ps aux | grep nginx
```