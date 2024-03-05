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
```

## Working with PostgreSQL

```bash
# pull the image
docker pull postgres

# run the container
docker run -e POSTGRES_PASSWORD=mysecretpassword postgres
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