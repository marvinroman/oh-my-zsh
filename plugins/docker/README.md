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

| Alias                | Command                                                                                                                          |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------------------|
| dps | docker ps --format "table {{.Names}}\t{{.Ports}}\t{{.Status}}\t{{.Image}}" | (read -r; printf "%s\n" "$REPLY"; sort -k 1 ) |
| dpsa | docker ps -a --format "table {{.Names}}\t{{.Ports}}\t{{.Status}}\t{{.Image}}" | (read -r; printf "%s\n" "$REPLY"; sort -k 1 ) |
| dlf | docker logs -f |
| dl | docker logs |
| dspr | docker system prune |
| dvpr | docker volume prune |
| dnpr | docker network prune |
| dipr | docker image prune |
| drm | docker rm |
| drmi | docker rmi |
| drund | docker run -d |
| drunit | docker run -it |
| drunrm | docker run --rm |
| drunrmit | docker run --rm -it |
| drunrmd | docker run --rm -d |
| dex | docker exec |
| dexit | docker exec -it |
| dbu | docker build -t |