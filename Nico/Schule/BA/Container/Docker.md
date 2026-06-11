---
Fach: "[[BA]]"
---
https://docs.docker.com/reference/cli/docker/
Docker ist ein Tool mit dem man Anwendungen in Containern laufen lassen kann.
# Commands
## Getting Started
Start a basic Container:
```sh
docker pull <imageName>
docker run -it --rm --name <ContainerName> <imageName> <TerminalEntrypoint>
```
`-it`: Interactive Terminal
`--rm`: Beim stoppen wird der Container gelöscht
`--name`: Name des laufendes Containers
`<TerminalEntrypoint>`: z.B. /bin/bash
## Information
| Command                      | Description                                        |
| ---------------------------- | -------------------------------------------------- |
| `docker ps`                  | List running containers                            |
| `docker ps -a`               | List all containers                                |
| `docker ps -s`               | List running containers  <br>_(with CPU / memory)_ |
| `docker images`              | List all images                                    |
| `docker inspect <container>` | Inspecting Containers                              |
| `docker events <container>`  | Containers Events                                  |
| `docker port <container>`    | Public Ports                                       |
| `docker top <container>`     | Running Processes                                  |
| `docker stats <container>`   | Container Resource Usage                           |
| `docker diff <container>`    | Lists the changes made to a container.             |
| `docker logs <container>`    | Container Logs                                     |
## Manipulate
| Command                                                     | Description                                             |
| ----------------------------------------------------------- | ------------------------------------------------------- |
| `docker exec -it <container-name-or-id> <shell-executable>` | Shell des Dockers aufrufen. Shell Beispiel: `/bin/bash` |
| `docker exec -it <container> bash`                          | Connecting to container                                 |
| `docker stop <container>`                                   | Stop a container                                        |
| `docker restart <container>`                                | Restart a container                                     |
| `docker rm <container>`                                     | Remove a container                                      |
| `docker port <container>`                                   | Shows container's port mapping                          |
| `docker top <container>`                                    | List processes                                          |
| `docker kill <container>`                                   | Kill a container                                        |
| ``docker rename <oldName> <newName>``                       | Renaming a Container                                    |
## Create
```bash
docker create [options] IMAGE
  -a, --attach               # attach stdout/err
  -i, --interactive          # attach stdin (interactive)
  -t, --tty                  # pseudo-tty
      --name NAME            # name your image
  -p, --publish 5000:5000    # port map (host:container)
      --expose 5432          # expose a port to containers
  -P, --publish-all          # publish all ports
      --link container:alias # linking
  -v, --volume hostPath:containerPath    # mount (absolute paths needed)
  -e, --env NAME=hello       # env vars
```

## Networking
| Command                                              | Description                                        |
| ---------------------------------------------------- | -------------------------------------------------- |
| `docker network rm MyOverlayNetwork`                 | Removing a network                                 |
| `docker network ls`                                  | Listing networks                                   |
| `docker network inspect MyOverlayNetwork`            | Getting information about a network                |
| `docker network connect MyOverlayNetwork nginx`      | Connecting a running container to a network        |
| `docker run -it -d --network=MyOverlayNetwork nginx` | Connecting a container to a network when it starts |
| `docker network disconnect MyOverlayNetwork nginx`   | Disconnecting a container from a network           |
## Clean
| Command                  | Description                                                                                        |
| ------------------------ | -------------------------------------------------------------------------------------------------- |
| `docker system prune`    | Cleans up dangling images, containers, volumes, and networks (ie, not associated with a container) |
| `docker system prune -a` | Additionally, remove any stopped containers and all unused images (not just dangling images)       |
| `docker rmi <image>`     | Removes image                                                                                      |
# Compose

| Command                                                     | Description                                                                                                                                                                                                                       |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `docker compose up -d`                                      | Lädt die Konfiguration der `docker-compose.yml` aus dem aktuellen Directory und fährt den Container hoch. Durch `-d` wird der Container im Hintergrund ausgeführt, und die Konsole verlässt den Container nach dem starten wieder |
| `docker compose down`                                       | Fährt den Container herunter                                                                                                                                                                                                      |
| `docker compose kill`                                       | Erzwingt das herunterfahren des Dockers                                                                                                                                                                                           |
| `docker compose pull`                                       | Lädt die neueste Version des Docker Images                                                                                                                                                                                        |
## docker-compose.yml
>Mit dieser Datei können Docker Container konfiguriert werden, und die Konfiguration gespeichert werden.

Eine Beispieldatei für eine `docker-compose.yml`.
```yaml
services:
  <service_name>:
    container_name: <container_name>
    image: <image_name>:<tag>
    pull_policy: <always|missing|never>
    restart: <no|always|on-failure|unless-stopped>
    hostname: <hostname>
    domainname: <domain>
    user: "<user>:<group>"
    group_add:
      - <group_id>
    entrypoint: ["<befehl>", "<arg1>", "<arg2>"]
    command: ["<befehl>", "<arg1>"]
    ports:
      - "<host_port>:<container_port>/<tcp|udp|sctp>:<ro/rw>"
    expose:
      - "<port>"
    volumes:
      - "<host_path>:<container_path>:<rw|ro>"
    environment:
      <VAR_NAME>: <VAR_VALUE>
    env_file:
      - <pfad/zur/.env>
    networks:
      - <network_name>

networks:
  <network_name>:
    driver: <bridge|overlay|host|none>
    driver_opts:
      <key>: <value>
    ipam:
      driver: <default>
      config:
        - subnet: <172.28.0.0/16>
          gateway: <172.28.5.254>
    external: <true|false>
    name: <netzwerk_name>

volumes:
  <volume_name>:
    driver: <local|nfs|...>
    driver_opts:
      <key>: <value>
    external: <true|false>
    name: <volumen_name>

```
# Dockerfile
---

| Instruction                                                                    | Description                                                                                                                                                                                              |
| ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`FROM <image>`](https://docs.docker.com/reference/dockerfile/#from)           | Defines a base for your image.                                                                                                                                                                           |
| [`RUN <command>`](https://docs.docker.com/reference/dockerfile/#run)           | Executes any commands in a new layer on top of the current image and commits the result. `RUN` also has a shell form for running commands.                                                               |
| [`WORKDIR <directory>`](https://docs.docker.com/reference/dockerfile/#workdir) | Sets the working directory for any `RUN`, `CMD`, `ENTRYPOINT`, `COPY`, and `ADD` instructions that follow it in the Dockerfile.                                                                          |
| [`COPY <src> <dest>`](https://docs.docker.com/reference/dockerfile/#copy)      | Copies new files or directories from `<src>` and adds them to the filesystem of the container at the path `<dest>`.                                                                                      |
| [`CMD <command>`](https://docs.docker.com/reference/dockerfile/#cmd)           | Lets you define the default program that is run once you start the container based on this image. Each Dockerfile only has one `CMD`, and only the last `CMD` instance is respected when multiple exist. |