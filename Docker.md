# Docker

## Commands

```bash
# list all containers
docker ps -a

# list all images
docker images

# remove a container
docker rm <container_id>

# remove an image
docker rmi <image_id>

# pull an image from docker hub
docker pull node:lts-alpine

# run a container from an image
docker run -it -p 3000:3000 -v $(pwd):/app/ node:lts-alpine

# stop a container
docker stop <container_id>

# Start a **container**
docker start <container_id>

# Start a container with different ports
docker run -it -p 3000:3000 -p 3001:3001 -v $(pwd):/app/ node:lts-alpine

# docker logs
docker logs <container_id>

# Docker container does not share the same data bases by default, for storing data in a container, we need to create a volume

# create a volume
docker volume create my-vol

# list all volumes
docker volume ls

# Add a local directory to a volume
docker run -it -p 3000:3000 -v $(pwd):/app/ -v my-vol:/app node:lts-alpine

# remove a volume
docker volume rm my-vol

# Mount your local directory to a container
docker run -it -p 3000:3000 -v $(pwd):/app/ node:lts-alpine

# Mount your local directory to a container with a volume
docker run -it -p 3000:3000 -v $(pwd):/app/ -v my-vol:/app/node_modules node:lts-alpine

# run a container with a volume
docker run -it -p 3000:3000 -v $(pwd):/app/ -v my-vol:/app/node_modules node:lts-alpine

# docker network ls
docker network ls

# Execute a command in a running container
docker exec -it <container_id> /bin/bash

# Docker ignore file
# .dockerignore

# Multi Stage Builds
# Dockerfile
# FROM node:lts-alpine as builder
# WORKDIR /app
# COPY . .
# RUN npm install
# RUN npm run build
# FROM nginx:alpine
# COPY --from=builder /app/build /usr/share/nginx/html


# Docker connect to a container with interactive mode
docker exec -it <container_id> /bin/bash


# Create a container from a docker file
docker build -t your-image-name .
docker run -d -p 3000:3000 your-image-name
```

## Working with PostgreSQL

```bash
# pull the image
docker pull postgres

# run the container
docker run -e POSTGRES_PASSWORD=mysecretpassword postgres
docker run -e POSTGRES_PASSWORD=mysecretpassword postgres:13.8
docker run --name postgres_13 -e POSTGRES_PASSWORD=mysecretpassword postgres:13.8
docker run --name postgres_latest -e POSTGRES_PASSWORD=mysecretpassword postgres
```

## Working with Mongo

```bash
# pull the image
docker pull mongo

# run the container
docker run --name some_mongo -d -p 27017:27017 mongo
```

## Working with MySQL

```bash
# pull the image
docker pull mysql

# run the container
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag
```

## Working with Redis

```bash
# pull the image
docker pull redis

# run the container
docker run --name some-redis -d redis

docker exec -it some-redis /bin/bash
```

## Working with MongoDB and Mongo Express

```bash

# pull the image
docker pull mongo
docker pull mongo-express

# run the container
docker run -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password  --name some-mongo --net mongo-network -p 27017:27017 mongo
docker run -d --name mongo-express --net mongo-network -e ME_CONFIG_MONGODB_SERVER=some-mongo -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password -p 8081:8081 mongo-express
```

## Working with Compose

```bash
# create a new compose file
# version: '3'
# services:
#   mongodb:
#     image: mongo
#     container_name: mongodb
#     environment:
#       MONGO_INITDB_ROOT_USERNAME: root
#       MONGO_INITDB_ROOT_PASSWORD: password
#     ports:
#       - 27017:27017
#   mongo-express:
#     image: mongo-express
#     container_name: mongo-express
#     environment:
#       ME_CONFIG_MONGODB_ADMINUSERNAME: root
#       ME_CONFIG_MONGODB_ADMINPASSWORD: password
#       ME_CONFIG_MONGODB_SERVER: mongodb
#     ports:
#       - 8081:8081

docker-compose -f docker-compose.yml up -d
docker-compose up -d
docker-compose down
```


### Push image to docker

```bash
# Create a DockerFile
# FROM python:3.8
# WORKDIR /app
# COPY . .
# RUN pip install -r requirements.txt
# CMD ["python", "app.py"]

# Build the image
docker build -t myusername/myapp:0.0.1.RELEASE .

# Run the Container
docker run -d -p 5000:5000 myusername/myapp:0.0.1.RELEASE

# Stop the Container
docker stop <container_id>

# Push the image
docker push myusername/myapp:0.0.1.RELEASE
```

### Simple Node serve for static files

<!-- File Structure -->

```
.
├── Dockerfile
├── web
│   ├── index.html
│   ├── main.js
│   └── style.css
```

<!-- Dockerfile -->

```Dockerfile
FROM node:lts-alpine
WORKDIR /app/
COPY . .    
RUN npm -y -g install serve
CMD ["serve", "web"]
```

### Docker Compose

```YAML
version: '3'
services:
  web:
    build: .
    ports:
      - "3000:3000"
```

### Docker Compose for Flutter

```YAML
version: '3'
services:
  web:
    build: .
    ports:
      - "3000:3000"
    environment:
      - API_URL=http://localhost:3000
```

### Docker Compose for Flutter with Firebase

```YAML
version: '3'
services:
  web:
    build: .
    ports:
      - "3000:3000"
    environment:
      - API_URL=http://localhost:3000
      - FIREBASE_API_KEY=YOUR_API_KEY
      - FIREBASE_AUTH_DOMAIN=YOUR_AUTH_DOMAIN
      - FIREBASE_PROJECT_ID=YOUR_PROJECT_ID
      - FIREBASE_STORAGE_BUCKET=YOUR_STORAGE_BUCKET
      - FIREBASE_MESSAGING_SENDER_ID=YOUR_MESSAGING_SENDER_ID
      - FIREBASE_APP_ID=YOUR_APP_ID
      - FIREBASE_MEASUREMENT_ID=YOUR_MEASUREMENT_ID
```


