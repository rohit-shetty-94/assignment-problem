# 📘 Project : Assignment Problem

##  Dockerize BOTH apps - the Python and the Node app.

### 1. Create appropriate images for both apps (two separate images!). HINT: Have a brief look at the app code to configure your images correctly!

cd inside both node & python project directory
```bash
-> create Dockerfile (Dockerfile are committed respectively)
-> run: docker build .
```

### 2. Launch a container for each created image, making sure, that the app inside the container works correctly and is usable.

```bash
-> node: docker run -p 8080:3000 <docker-image-id>
-> python: docker run -it <docker-image-id>
```

### 3. Re-create both containers and assign names to both containers. Use these names to stop and restart both containers.

```bash
-> python 
    image build with name -> docker build -t python:latest .
    ex: docker build -t <image-name>:<image-tag> .
    container run with name -> docker run -it --name py-con python:latest 
    ex: docker run -it --name <container-name> <image-name>:<image-tag>

-> node 
    image build with name -> docker build -t node:latest .
    container run with name -> docker run -p 8080:3000 --name node-con node:latest 
```

### 4. Clean up (remove) all stopped (and running) containers, clean up all created images.

```bash
images cleanup -> docker rmi <image-name> / <image-id>
container cleanup -> docker rm <container-name> / <container-id> 
```

### 5. Re-build the images - this time with names and tags assigned to them.

```bash
image build with name -> docker build -t node:latest .
ex: docker build -t <name>:<tag> .
```

### 6. Run new containers based on the re-built images, ensuring that the containers are removed automatically when stopped.

```bash
docker run -it --rm --name py-con-rm python:latest
ex: docker run -it --rm --name <container-name> <image-name>:<image-tag>
```