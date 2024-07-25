Login to ghcr.io

```sh
echo $CR_PAT | docker login ghcr.io -u faraday-law --password-stdin
```

Build images
```sh
docker build --platform linux/amd64 -t ghcr.io/faraday-law/mkdocs -f Dockerfile.mkdocs .

docker build --platform linux/amd64 -t ghcr.io/faraday-law/caddy -f Dockerfile.caddy .
```

Push images
```sh
docker push ghcr.io/faraday-law/caddy:latest
docker push ghcr.io/faraday-law/mkdocs
```

Run
```sh
docker-compose up -d
```