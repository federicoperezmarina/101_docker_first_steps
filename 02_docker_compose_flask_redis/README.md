## Docker Compose Flask Redis
### Flask & Redis

[docker-compose.yml](docker-compose.yml)
```sh
version: "3.9"
services:
  web:
    build: .
    ports:
      - "5000:5000"
  redis:
    image: "redis:alpine"
```

## Deploy with docker-compose
```sh
$ docker-compose up -d
Starting 02_docker_compose_flask_redis_redis_1 ... done
Starting 02_docker_compose_flask_redis_web_1   ... done
```

## Expected result

Listing containers must show three containers running and the port mapping as below:
```sh
$ docker ps
CONTAINER ID   IMAGE                               COMMAND                  CREATED         STATUS          PORTS                    NAMES
711ae1c1c5e9   02_docker_compose_flask_redis_web   "flask run"              2 minutes ago   Up 23 seconds   0.0.0.0:5000->5000/tcp   02_docker_compose_flask_redis_web_1
67f6d299658e   redis:alpine                        "docker-entrypoint.s…"   2 minutes ago   Up 23 seconds   6379/tcp                 02_docker_compose_flask_redis_redis_1                                               es
```

After the application starts, navigate to below links in your web browser:

* Flask: [`http://localhost:5000`](http://localhost:5000)

Stop and remove the containers
```sh
docker-compose down
```