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

### Uptime Kuma

Uptime Kuma provides service and endpoint monitoring. Its Compose configuration is located at `docker/uptime-kuma/compose.yaml`.

Start it from the repository root:

```bash
docker compose -f docker/uptime-kuma/compose.yaml up -d
```

After it starts, open `http://<docker-host-ip>:3001`.

### Homarr

Homarr provides a dashboard for homelab services. Its Compose configuration is located at `docker/homarr/compose.yaml`.

Generate and store the required encryption key before the first start:

```bash
printf 'SECRET_ENCRYPTION_KEY=%s\n' "$(openssl rand -hex 32)" > docker/homarr/.env
```

Keep this key unchanged and backed up. Homarr uses it to encrypt secrets stored in its database.

Start Homarr from the repository root:

```bash
docker compose -f docker/homarr/compose.yaml up -d
```

After it starts, open `http://<docker-host-ip>:7575`.
