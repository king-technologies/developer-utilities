# Docker Image

```dockerfile
FROM ubuntu:18.04
LABEL maintainer="

# CMD ["echo", "Hello World"]
# ENTRYPOINT ["echo", "Hello World"] // This will override CMD command, it is used to run the container in the foreground
# CMD ["echo", "Hello World"] // This will run the container in the background
```