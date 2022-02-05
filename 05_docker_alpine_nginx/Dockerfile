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
