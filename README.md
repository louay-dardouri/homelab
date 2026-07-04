# homelab

Single-node Docker Compose homelab running on Linux. Services are organized into
independent stacks, each in its own directory with a `docker-compose.yaml` and
optional `.env` file (gitignored).


## Running Services

Each stack is independent and deployed separately. From the repo root:

    cd arr && docker compose up -d

To deploy everything at once:

    for dir in */; do (cd "$dir" && docker compose up -d); done

To tear down a specific stack:

    cd arr && docker compose down

First-time setup requires the external network:

    docker network create homelab_network

## Reverse Proxy

Nginx runs as a systemd service on the host (outside Docker) and terminates
TLS for web-facing services on ports 80/443.
