Run MongoDB locally with Docker/podman
```
podman pull mongo
podman volume create mongodb_data
podman run -d -p 27017:27017 -v mongodb_data:/data/db --name mongodb mongo
```