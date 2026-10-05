# Homelab

This repository contains the Docker Compose services for my homelab. The environment is being rebuilt from scratch, with each service stored in its own directory under `docker/`.

## Services

### Dockhand

Dockhand is the first service in the rebuilt homelab. Its Compose configuration is located at `docker/dockhand/compose.yaml`.

Start it from the repository root:

```bash
docker compose -f docker/dockhand/compose.yaml up -d
```

After it starts, open `http://<docker-host-ip>:3000`.
