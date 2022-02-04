FROM ubuntu:latest

COPY message.py /tmp/message.py

RUN apt-get update && \
    apt-get install -y python3 && \
    apt-get install -y python3-pip && \    
    pip3 install requests

CMD ["python3", "/tmp/message.py"]