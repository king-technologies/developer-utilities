# Postgres with Docker

## Introduction
Docker makes it easy to run databases like Postgres in isolated, reproducible environments. This lesson covers how to run Postgres using Docker, including key concepts like images, containers, volumes, and configuration.

## What is Docker?
Docker is a platform for developing, shipping, and running applications in containers. Containers are lightweight, portable, and ensure consistency across environments.

## What is Postgres?
Postgres (PostgreSQL) is a powerful, open-source relational database system.

## Why Use Docker for Postgres?
- **Isolation:** Each database runs in its own container.
- **Reproducibility:** Easily recreate environments.
- **Simplicity:** No need to install Postgres directly on your machine.

## Key Concepts
- **Image:** A snapshot of a filesystem and configuration. The official Postgres image is available on Docker Hub.
- **Container:** A running instance of an image.
- **Volume:** A persistent storage mechanism. Volumes allow you to keep your database data even if the container is removed.

## Running Postgres with Docker

### 1. Pull the Postgres Image
```sh
docker pull postgres
```

### 2. Run a Postgres Container
```sh
docker run --name my-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```
- `--name my-postgres`: Names the container.
- `-e POSTGRES_PASSWORD=...`: Sets the database password.
- `-d`: Runs the container in detached mode.
- `postgres`: The image to use.

### 3. Expose Ports
To connect from your host machine:
```sh
docker run --name my-postgres -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d postgres
```
- `-p 5432:5432`: Maps container port 5432 to host port 5432.
6
### 4. Using Volumes for Data Persistence
```sh
docker run --name my-postgres -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -v pgdata:/var/lib/postgresql/data -d postgres
```
- `-v pgdata:/var/lib/postgresql/data`: Mounts the named volume `pgdata` to the Postgres data directory.

### 5. Connecting to Postgres
You can connect using any Postgres client, e.g.:
```sh
psql -h localhost -U postgres
```
Password: `mysecretpassword`

**Postgres Connection String Example:**
```
postgresql://postgres:mysecretpassword@localhost:5432/postgres
```
- `postgres`: username
- `mysecretpassword`: password
- `localhost`: host
- `5432`: port
- `postgres`: database name

Or, connect from inside the container:
```sh
docker exec -it my-postgres psql -U postgres
```

### 6. Stopping and Removing the Container
```sh
docker stop my-postgres
```
```sh
docker rm my-postgres
```

### 7. Removing the Volume (if needed)
```sh
docker volume rm pgdata
```

## Common Configuration Options
- `POSTGRES_USER`: Set the database user (default: `postgres`).
- `POSTGRES_PASSWORD`: Set the password for the user.
- `POSTGRES_DB`: Set the default database name.

Example:
```sh
docker run --name my-postgres -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=secret -e POSTGRES_DB=mydb -d postgres
```

## Summary
- Use Docker to quickly run and manage Postgres containers.
- Use volumes for persistent data.
- Configure environment variables for user, password, and database.

## Quiz

### Question 1
What does the `-v pgdata:/var/lib/postgresql/data` option do?
- [ ] Exposes the database on a different port
- [x] Persists database data outside the container
- [ ] Sets the Postgres password
- [ ] Names the container

### Question 2
Which command connects you to the running Postgres container's shell?
- [ ] docker run -it my-postgres bash
- [x] docker exec -it my-postgres psql -U postgres
- [ ] docker connect my-postgres
- [ ] docker attach my-postgres

### Question 3
What is the default Postgres user created by the official image?
- [x] postgres
- [ ] admin
- [ ] root
- [ ] user

