FROM alpine:latest

COPY message.js /tmp/message.js

RUN apk add --update nodejs npm

CMD ["node", "/tmp/message.js"]