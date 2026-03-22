# Qdrant on Ubuntu (Docker Compose)

Run [Qdrant](https://qdrant.tech/) vector database via Docker Compose on Ubuntu.

## Prerequisites

- **Docker** and **Docker Compose** on Ubuntu:
  ```bash
  sudo apt update
  sudo apt install -y docker.io docker-compose-plugin
  sudo systemctl start docker
  sudo systemctl enable docker
  ```
- Add your user to the `docker` group to run without `sudo`:  
  `sudo usermod -aG docker $USER` (then log out and back in).

## Usage

**Start Qdrant (detached):**
```bash
sudo docker compose up -d
```

**Stop Qdrant:**
```bash
sudo docker compose down
```

**Stop and remove stored data:**
```bash
sudo docker compose down -v
```

## Endpoints

| Service        | URL |
|----------------|-----|
| Web dashboard  | http://localhost:6333/dashboard |
| REST API       | http://localhost:6333 |
| Health check   | http://localhost:6333/healthz |
| gRPC           | localhost:6334 |

Data is persisted in the Docker volume `qdrant_storage` and survives container restarts.

## Other machine (e.g. Mac on same LAN):

| Service        | URL |
|----------------|-----|
| Web dashboard  | http://192.168.86.179:6333/dashboard |
| REST API       | http://192.168.86.179:6333 |
| Health check   | http://192.168.86.179:6333/healthz |
| gRPC           | 192.168.86.179:6334 |
