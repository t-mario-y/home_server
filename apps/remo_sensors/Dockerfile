FROM denoland/deno:debian-1.46.3

EXPOSE 8000

USER deno
WORKDIR /app

COPY . .
RUN deno cache main.ts

CMD ["run", "--allow-net", "main.ts"]
