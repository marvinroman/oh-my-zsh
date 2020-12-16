# Docker plugin

This plugin adds auto-completion for [docker](https://www.docker.com/).

To use it add `docker` to the plugins array in your zshrc file.

```zsh
plugins=(... docker)
```

A copy of the completion script from the docker/cli git repo:
https://github.com/docker/cli/blob/master/contrib/completion/zsh/_docker

## Settings

By default, the completion doesn't allow option-stacking, meaning if you try to
complete `docker run -it <TAB>` it won't work, because you're _stacking_ the
`-i` and `-t` options.

[You can enable it](https://github.com/docker/cli/commit/b10fb43048) by **adding
the lines below to your zshrc file**, but be aware of the side effects:

> This enables Zsh to understand commands like `docker run -it
> ubuntu`. However, by enabling this, this also makes Zsh complete
> `docker run -u<tab>` with `docker run -uapprox` which is not valid. The
> users have to put the space or the equal sign themselves before trying
> to complete.
>
> Therefore, this behavior is disabled by default. To enable it:
>
> ```
> zstyle ':completion:*:*:docker:*' option-stacking yes
> zstyle ':completion:*:*:docker-*:*' option-stacking yes
> ```

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