# Docker Cheat Sheet

## Run

Creates and starts a container

```
docker run ${IMAGE}
```

Options:

<table>
    <tr>
        <th>Option</tdh>
        <th>Description</th>
        <th>Example</th>
    </tr>
    <tr>
        <td>--expose</td>
        <td>Expose a port or a range of ports</td>
        <td>docker run --expose:7000-8000 node</td>
    </tr>
    <tr>
        <td>-d</td>
        <td>Run container in the background</td>
        <td>docker run -d node</td>
    </tr>
    <tr>
        <td>--name</td>
        <td>Assign name to a container</td>
        <td>docker run --name="MyNodeContainer" node</td>
    </tr>
    <tr>
        <td>-p</td>
        <td>Binds a container port to a host port</td>
        <td>docker run -p 3000:300 node</td>
    </tr>
    <tr>
        <td>--rm</td>
        <td>Removes the container when it exits</td>
        <td>docker run --rm node</td>
    </tr>
    <tr>
        <td>-it</td>
        <td>Allocate a pseudo-TTY (Creates an interactive bash)</td>
        <td>docker run -it node</td>
    </tr>
    <tr>
        <td>-v</td>
        <td>Bind mount a volume</td>
        <td>docker run -v "app":"app" node</td>
    </tr>
    <tr>
        <td>-w</td>
        <td>Set working directory inside the container</td>
        <td>
        docker run -w /app node
        </td>
    </tr>    
</table>


## Build

Builds an image from a Dockerfile

```bash
docker [options] build $IMAGE .
```

Options:

<table>
    <tr>
        <th>Option</tdh>
        <th>Description</th>
        <th>Example</th>
    </tr>
    <tr>
        <td>-f</td>
        <td>Specify the name of the Dockerfile</td>
        <td>docker build -f build/Dockerfile myImage</td>
    </tr>
    <tr>
        <td>-t</td>
        <td>Add a name tag to an image</td>
        <td>docker build -t alesandrog/node:2.0</td>
    </tr>  
</table>


## Manage Images and Containers

### Images


###### List all images

```bash
docker image ls
```

```bash
docker images 
```

###### Remove images

```bash
docker image rm ${IMAGE_ID | IMAGE_NAME}
```
```bash
docker rmi ${IMAGE_ID | IMAGE_NAME}
```
### Containers

###### Start existing container

```bash
docker start ${CONTAINER_ID | CONTAINER_NAME}
```

###### Stop running container

```bash
docker stop ${CONTAINER_ID | CONTAINER_NAME}
```

###### List running containers

```bash
docker ps
```

###### List all containers
```bash
docker ps -a
```

###### Remove containers
```bash
docker rm ${CONTAINER_ID | CONTAINER_NAME}
```

### Logs

Shows information logged by a running container.

```bash
docker logs  ${CONTAINER_ID | CONTAINER_NAME}
```

### Execute an interactive bash

```bash
docker exec -it  ${CONTAINER_ID | CONTAINER_NAME} /bin/bash
```

