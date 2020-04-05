Docker compose file for easy vanilla server deployment.

# How to setup
1. Install [Docker-compose](https://docs.docker.com/compose/install/), [Git](https://www.linode.com/docs/development/version-control/how-to-install-git-on-linux-mac-and-windows/)
2. Clone this repository ``` git clone https://github.com/ustymenkopavlo/minecraft-dockercompose-vanila-server.git ```
3. Enter ``` cd minecraft-dockercompose-vanila-server/ ``` then ``` docker-compose up -d ```

# Modify 
To use a different Minecraft version, pass the ``` VERSION ``` environment variable, which can have the value
```
VERSION: "X.X.X"

```
You also can easy setup server with mods. Just add this variables to ```environment```

```
TYPE: "FORGE"
FORGEVERSION: "X.X.X.X"
```
Create ```mods``` volume and put mods-files to mods folder. (Create mod folder next to ```world/```)
```
....
    volumes: 
        - ./world:/data/world:rw
        - ./mods:/data/mods:rw
volumes: 
    world:
    mods:
....
```
You also can create ```configs``` volume
```
    volumes: 
        ...
        - ./config:/data/config:rw
volumes: 
    ...
    config:
```

# IMPORTANT
** This is an adaptation of [itzg`s](https://hub.docker.com/u/itzg) [Docker image](https://hub.docker.com/r/itzg/minecraft-server/) to Docker-compose **