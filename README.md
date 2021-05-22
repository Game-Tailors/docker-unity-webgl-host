# docker-unity-webgl-host
A docker configuration for a WebGL host


## How to use
The container expects a volume to be on `/webgl` containing the actual build. Other than that, it should "just work".

Example of a docker command to run this would be:
```
docker run -p 8080:80 -v /path/to/webgl/build/on/host:/webgl:ro --name webgl-test gametailors/unity-webgl-server
```

### Brotli compression
Brotli compression is supported, but requires SSL to work in e.g. Firefox. To do this when testing locally:
  1. Install [mkcert](https://github.com/FiloSottile/mkcert).
  2. Run:
     ```
     mkcert -cert-file certs/game.local.crt -key-file certs/game.local.key game.local
     ```
  3. In your [hosts file](https://en.wikipedia.org/wiki/Hosts_(file)), add the following:
     ```
     127.0.0.1     game.local
     ::1           game.local
     ```
  4. Run the attached docker-compose file: `docker-compose up -d`

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