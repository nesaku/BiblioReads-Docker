[![Publish Docker Image](https://github.com/nesaku/BiblioReads-Docker/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/nesaku/BiblioReads-Docker/actions/workflows/docker-publish.yml)

# BiblioReads Docker Image

Docker Image For [BiblioReads](https://github.com/nesaku/BiblioReads).

Published on Docker Hub at [nesaku/biblioreads](https://hub.docker.com/r/nesaku/biblioreads).

## Installation:

### Docker CLI:

```
docker run -d \
  --name biblioreads \
  -p 3000:3000 \
  --restart unless-stopped \
  -e NEXT_PUBLIC_HOST_URL=http://biblioreads.local \
  -e NEXT_TELEMETRY_DISABLED=1 \
  nesaku/biblioreads:latest
```

### Docker-Compose:

1. Download (or copy) `docker-compose.yml` from [here](https://github.com/nesaku/BiblioReads-Docker/blob/main/docker-compose.yml).
2. Edit or add environment variables to the `docker-compose.yml`
   - A full list of environment variables can be found [here](https://github.com/nesaku/BiblioReads/blob/main/.env.local.example)
3. Run the command `docker-compose up -d` to start the container
