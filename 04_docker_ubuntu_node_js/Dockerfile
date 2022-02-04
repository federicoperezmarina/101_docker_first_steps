FROM ubuntu:latest

COPY message.js /tmp/message.js

RUN apt-get update && \
	apt-get install -y nodejs && \
	apt-get install -y npm

CMD ["node", "/tmp/message.js"]