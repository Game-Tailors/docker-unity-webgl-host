# docker-unity-webgl-host
A docker configuration for a WebGL host


## How to use
The container expects a volume to be on `/webgl` containing the actual build. Other than that, it should "just work".

Example of a docker command to run this would be:
```
docker run -p 8080:80 -v /path/to/webgl/build/on/host:/webgl:ro --name webgl-test gametailors/unity-webgl-server
```

## Build
To build the container, run:
```
docker build --tag gametailors/unity-webgl-server .
```

## Publish
Run the command:
```
docker push gametailors/unity-webgl-server
```