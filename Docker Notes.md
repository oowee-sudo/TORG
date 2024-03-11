Docker:
- **`docker run`** : `-p` redirect port `-d` detach `-ti` interactive `-env` env `-v` mount volume  `-w` workdir `echo cmd` .
- **`docker stop id`**
- **`docker rm id`**
- **`docker pull image`**
- **`docker ps`**
- **`docker images -a`**
- **`docker system prune`** clean cache, off containers, non used images, networks
- **`docker tag id user/image:latest`**
- **`docker search image`**
- **`docker push image`**
- **``docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' id``**
Docker compose: 
- **`docker-compose up -d`**
- **`docker-compose ps`**
- **`docker-compose logs -f --tail 5`** 
- **`docker-compose stop`** 
- **`docker-compose down`** destroy stack resources.
- **`docker-compose config`** verify config file `docker-compose.yml`.
Dockerfile:
- **`FROM`**: Specifies the base image for the new image being built.
- **`RUN`**: Executes a command during the build process and saves the result to a new layer in the image.
- **`ADD`**: Copies files from the host machine into the image .
- **`WORKDIR`**: Sets the working directory for any subsequent instructions in the Dockerfile.
- **`EXPOSE`**: Documents the network ports that the container listens on at runtime.
- **`VOLUME`**: Creates a mount point for external volumes.
- **`CMD`**: Provides defaults for an executing container, including the command to run.
Example: 
  ```Dockerfile
FROM debian:9

RUN apt-get update -yq \
&& apt-get install curl gnupg -yq \
&& curl -sL https://deb.nodesource.com/setup_10.x | bash \
&& apt-get install nodejs -yq \
&& apt-get clean -y

ADD . /app/
WORKDIR /app
RUN npm install

EXPOSE 2368
VOLUME /app/logs

CMD npm run start
```
docker-compose.yaml:
- **`image`**: Specifies the name or tag of the Docker image.
- **`build`**: Specifies the path to the Dockerfile used to build the Docker image.
- **`volume`**: Specifies the path to share files and directories between the host and the container.
- **`restart`**: Sets the restart policy for the container.
- **`environment`**: Sets environment variables for the container.
- **`depends_on`**: Specifies the services or containers that need to be started before the current service or container.
- **`ports`**: Sets the port mapping between the host and the container.
Example:
```yaml
version: '3'
services:
  db:
    image: mysql:5.7
    volumes:
      - db_data:/var/lib/mysql
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: somewordpress
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress
    
  wordpress:
    depends_on:
      - db
    image: wordpress:latest
    ports:
      - "8000:80"
    restart: always
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress

volumes:
  db_data: {}
```