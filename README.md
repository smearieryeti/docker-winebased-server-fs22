![FS22](https://raw.githubusercontent.com/wine-gameservers/docker-winebased-server-fs22/main/misc/fs22_top_logo.png "Farming Simulator 22")

# docker-winebased-server-fs22

Farming Simulator 22 server running inside a Docker Container (with [vnc](#vnc)
This project is maintained at [wine-gameservers/docker-winebased-server-fs22](https://github.com/wine-gameservers/docker-winebased-server-fs22) 

Please note this project is missing crucial documentation regarding the usage and requirements for running this docker container, currently this information is only available in our Discord server listed in the footer of this readme.

**Description**

This is the first beta verion to be released!
  
# Table of contents

* [Basic Docker Usage](#basic-docker-usage)
* [System requirements](#system-requirements)
* [Environment Variables](#environment-variables)

* [Configuration](#configuration)

* [vnc](#vnc)

* [Status web server](#status-web-server)


# Basic Docker Usage

```
docker run -d \
    --name docker-fs22-server \
    --cap-add=sys_nice \
    -p 5900:5900/tcp \
    -p 8080:8080/tcp \
    -p 9000:9000/tcp \
    -p 10823:10823/tcp \
    -p 10823:10823/udp \
    -v /etc/localtime:/etc/localtime:ro \
    -v /opt/fs22_installer:/installer_files \
    -e USERNAME="FS22USER" \
    -e VNC_PASSWORD="FS22USER" \
    -e WEB_USERNAME="FS22USER" \
    -e WEB_PASSWORD="FS22USER" \
    -e SERVER_NAME="Docker Server" \
    -e SERVER_ADMIN="FS22USER" \
    -e SERVER_PASSWORD="FS22USER" \
    -e SERVER_PLAYERS="16" \
    -e SERVER_PORT="10823" \
    -e SERVER_REGION="en" \
    -e SERVER_MAP="MapUS" \
    -e SERVER_DIFFICULTY="3" \
    -e SERVER_PAUSE="2" \
    -e SERVER_SAVE_INTERVAL="180.000000" \
    -e SERVER_STATS_INTERVAL="31536000" \
    -e SERVER_CROSSPLAY="true" \
    wine-gameservers/docker-winebased-server-fs22
```

# Environment Variables
**All variable names and values are case-sensitive!**

| Name | Default | Purpose |
|----------|----------|-------|
| `USERNAME` | `FS22USER` | The username used inside the docker container |
| `VNC_PASSWORD` | `FS22USER` | Password for connecting using the VNC client |
| `WEB_USERNAME` | `FS22USER` | Username for admin portal at :8080 |
| `SERVER_NAME` | `Docker Server` | Name that will be shown in the server browser |
| `SERVER_PORT` | `10823` | Default: 10823, port that the server will listen on |
| `SERVER_ADMIN` | `FS22USER` | Default: FS22USER", admin username for the game |
| `SERVER_PASSWORD` | `FS22USER` | Default: FS22USER", server password for the game |
| `SERVER_REGION` | `en,de,nl` | I still need to grab all supported country letters, this will be updated asap... |
| `SERVER_PLAYERS` | `16` | Default: 16 amount of players allowed on the server |
| `SERVER_MAP` | `MapUS` | Default: MapUS, need to grab the other names will update asap! |
| `SERVER_DIFFICULTY` | `3` | Default: 3, start from scratch |
| `SERVER_PAUSE` | `2` | Default: 2 Pause the server if no players are connected 1, never pause the server |
| `SERVER_SAVE_INTERVAL` | `180.000000` | Default:180.000000, in seconds |
| `SERVER_STATS_INTERVAL` | `31536000` | Default: 120.000000, webapi is not supported anymore for FS22 so lets give it an odd number so it doesen't spam the logs |
| `SERVER_CROSSPLAY` | `true/false` | Default:true |

# Discord

Want to help or contribute by testing? join my discord!

https://discord.gg/57EY9pmg9U

# Legal disclaimer
This Docker container is not endorsed by, directly affiliated with, maintained, authorized, or sponsored by [Giants Software](https://giants-software.com) and [Farming Simulator 22](https://farming-simulator.com/). The logo [Farming Simulator 22](https://giants-software.com) are © 2021 Giants Software.
