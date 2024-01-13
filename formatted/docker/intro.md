# Docker

## What is Docker?

- Docker is a tool designed to make it easier to create, deploy, and run applications by using containers.
- Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and ship it all out as one package.
- By doing so, thanks to the container, the developer can rest assured that the application will run on any other Linux machine regardless of any customized settings that machine might have that could differ from the machine used for writing and testing the code.
- In a way, Docker is a bit like a virtual machine. But unlike a virtual machine, rather than creating a whole virtual operating system, Docker allows applications to use the same Linux kernel as the system that they're running on and only requires applications be shipped with things not already running on the host computer.
- This gives a significant performance boost and reduces the size of the application.
- Docker is a tool that's designed to benefit both developers and system administrators, making it a part of many DevOps (developers + operations) toolchains.
- For developers, it means that they can focus on writing code without worrying about the system that it will ultimately be running on.
- It also allows them to get a head start by using one of thousands of programs already designed to run in a Docker container as a part of their application.
- For operations staff, Docker gives flexibility and potentially reduces the number of systems needed because of its small footprint and lower overhead.
- It also allows the staff to focus on the environment that the application runs in, rather than worry about the infrastructure that the application runs on.
- Docker provides the ability to package and run an application in a loosely isolated environment called a container.
- The isolation and security allow you to run many containers simultaneously on a given host.
- Containers are lightweight because they don't need the extra load of a hypervisor, but run directly within the host machine's kernel.

## Docker Architecture

- Docker uses a client-server architecture.
- The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers.
- The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon.
- The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface.


### Commands

- `docker version` - To check the version of docker
- `docker info` - To check the information of docker
- `docker` - To check the list of commands
- `docker run hello-world` - To run the hello-world image
- `docker images` - To check the list of images
- `docker ps` - To check the list of running containers
- `docker ps -a` - To check the list of all containers
- `docker pull <image-name>` - To pull the image from docker hub
- `docker run <image-name>` - To run the image
- `docker run -it <image-name>` - To run the image in interactive mode
- `docker run -it <image-name> bash` - To run the image in interactive mode with bash
- `docker run -it <image-name> sh` - To run the image in interactive mode with sh
- `docker tag <image-name> <username>/<image-name>:<version>` - To tag the image with username and version
- `docker push <username>/<image-name>:<version>` - To push the image to docker hub