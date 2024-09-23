dev env(native)
```
deno task start
```

dev env(docker)
````
docker buildx build --platform linux/arm64 --tag remo_sensors:latest .
docker run -p 8000:8000 remo_sensors:latest
````
