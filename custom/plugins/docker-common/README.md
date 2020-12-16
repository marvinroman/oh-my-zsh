# Docker Common Aliases plugin

## Aliases

| Alias | Command | Description |
|:----|:----:|:----|
| `dps` | `docker ps --format "table {{.Names}}\t{{.Ports}}\t{{.Status}}\t{{.Image}} \| (read -r; printf "%s\n" "$REPLY"; sort -k 1 )` | Pretty print processes |
| `dpsa` | `docker ps -a --format "table {{.Names}}\t{{.Ports}}\t{{.Status}}\t{{.Image}}" \| (read -r; printf "%s\n" "$REPLY"; sort -k 1 )` | Pretty print processes include all |
| `dlf` | `docker logs -f` | View container logs and follow |
| `dl` | `docker logs` | View container logs |
| `dspr` | `docker system prune` | Prune containers, images, networks & build cache |
| `dvpr` | `docker volume prune` | Prune volumes |
| `dnpr` | `docker network prune` | Prune networks |
| `dipr` | `docker image prune` | Prune images |
| `drm` | `docker rm` | Remove container |
| `drmi` | `docker rmi` | Remove image |
| `drund` | `docker run -d` | Run container daemonized |
| `drunit` | `docker run -it` | Run container with interactive terminal |
| `drunrm` | `docker run --rm` | Run container and remove after stopping |
| `drunrmit` | `docker run --rm -it` | Run container with interactive terminal and remove after stopping |
| `drunrmd` | `docker run --rm -d` | Run daemonized container and remove after stopping |
| `dex` | `docker exec` | Run process in container |
| `dexit` | `docker exec -it` | Enter container with interactive terminal |
| `dbu` | `docker build -t` | Build image |