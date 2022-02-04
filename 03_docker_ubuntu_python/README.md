# Dockerfile: Ubuntu-python
Now we are going to show how to create an image with a dockerfile using ubuntu distribution, installing python and executing a python command.

```sh
# Dockerfile content
FROM ubuntu:latest

COPY message.py /tmp/message.py

RUN apt-get update && \
    apt-get install -y python3 && \
    apt-get install -y python3-pip && \
    pip3 install requests

CMD ["python3", "/tmp/message.py"]
```

First of all we have to build the image:
```sh
# docker build 
docker build -t ubuntu-python .
```

Second execute the docker image:
```sh
docker run -it ubuntu-python

#output
My first Ubuntu docker image with python
```

Third we can get into the image and see if the library requests is installed
```sh
docker run -it ubuntu-python /bin/bash
pip3 list
```