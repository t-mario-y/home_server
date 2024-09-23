dev env(native)
```sh
deno task start
deno run --allow-net main.ts
```

dev env(docker)
```sh
docker buildx build --platform linux/arm64 --tag remo_sensors:latest .
docker run -p 8000:8000 remo_sensors:latest

```

push image to ECR
