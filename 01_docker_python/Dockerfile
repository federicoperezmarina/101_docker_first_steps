FROM alpine:latest

COPY message.py /tmp/message.py

RUN apk add python3 && \
    apk add py3-pip && \    
    pip3 install requests

CMD ["python3", "/tmp/message.py"]