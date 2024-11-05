[![Publish Docker Image](https://github.com/nesaku/BiblioReads-Docker/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/nesaku/BiblioReads-Docker/actions/workflows/docker-publish.yml)

# BiblioReads Docker Image

Docker Image For [BiblioReads](https://github.com/nesaku/BiblioReads)

## Installation:

### Docker CLI:

```
docker run -d \
  --name biblioreads \
  -p 3000:3000 \
  --restart unless-stopped \
  nesaku/biblioreads:latest
```

### Docker-Compose:

1. Download (or copy) `docker-compose.yml`
2. Edit or add environment variables to the `docker-compose.yml` file
3. Run the command `docker-compose up -d`
