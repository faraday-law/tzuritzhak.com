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
docker push ghcr.io/faraday-law/caddy
docker push ghcr.io/faraday-law/mkdocs
```

Add env vars
```sh
vim ~/.bashrc
export CR_PAT=<token>
export CLOUDFLARE_API_TOKEN=<token>
```

or `.env` file in the same directory with `docker-compose.yaml`
```sh
CR_PAT=<token>
CLOUDFLARE_API_TOKEN=<token>
```

Run
```sh
docker pull ghcr.io/faraday-law/caddy
docker pull ghcr.io/faraday-law/mkdocs
docker-compose up -d
```
