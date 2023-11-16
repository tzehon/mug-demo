Run MongoDB locally with Docker/podman
```
podman pull mongo
podman volume create mongodb_data
podman network create mug-network
podman run -p 27017:27017 --net=mug-network -v mongodb_data:/data/db --name mongodb mongo
podman run --net=mug-network --env-file=dev.env -p 3000:3000 mug-demo
```

Run app to connect to MongoDB-in-container
```
podman run --net=mug-network --env-file=podman.env -p 3000:3000 mug-demo
```

Run app to connect to local Atlas
```
podman run --env-file=atlas.env -p 3000:3000 mug-demo
```