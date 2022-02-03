# Dockerfile: Alpine-python
Now we are going to show how to create an image with a dockerfile using alpine distribution, installing python and executing a python command.

```sh
# Dockerfile content
FROM alpine:latest

COPY message.py /tmp/message.py

RUN apk add python3 && \
    apk add py3-pip && \
    pip3 install requests

CMD ["python3", "/tmp/message.py"]
```

First of all we have to build the image:
```sh
# docker build 
docker build -t alpine-python .
```

Second execute the docker image:
```sh
docker run -it alpine-python

#output
My first Alpine docker image with python
```