# homeserver

Collection of docker-composes that deploys a Linux-based media server infrastructure. This is mainly a personal project so changes, instability and fails are expected.

## Current infrastructure

### Intel® NUC NUC8i3BEH

* CPU: Intel i3-8109U @ 3.6GHz
* iGPU: Intel® Iris® Plus 655
* RAM: 1x16GB DDR4
* Storage: 1x1Tb SSD NMVE
* OS: Ubuntu-server 21.10 (Impish Indri)
* Docker: 20.10.12
* Docker-compose: 1.27.4

### Raspberry Pi 3 Model B+

* Storage: 16Gb SD Card
* Raspberry Pi TV HAT
* OS: Alpine Linux aarch64 (Data Disk Mode)

## Services
<img src="https://raw.githubusercontent.com/linuxserver/Heimdall-Apps/master/AdGuardHome/adguardhome.png" width="50" height="50"> <img src="https://logosarchive.com/wp-content/uploads/2021/08/Minecraft-icon.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/linuxserver/Heimdall-Apps/master/Overseerr/overseerr.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/linuxserver/Heimdall-Apps/master/Plex/plex.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/linuxserver/Heimdall-Apps/master/Prowlarr/prowlarr.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/linuxserver/Heimdall-Apps/master/qBittorrent/qbittorrent.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/linuxserver/Heimdall-Apps/master/Radarr/radarr.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/AnalogJ/scrutiny/master/webapp/frontend/src/assets/images/logo/scrutiny-logo-dark.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/linuxserver/Heimdall-Apps/master/Sonarr/sonarr.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/henrywhitaker3/Speedtest-Tracker/master/public/icons/fav/ms-icon-150x150.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/linuxserver/Heimdall-Apps/master/Tautulli/tautulli.png" width="50" height="50"> <img src="https://avatars.githubusercontent.com/u/6837578" width="50" height="50"> <img src="https://github.com/linuxserver/Heimdall-Apps/blob/master/Traefik/traefik.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/containrrr/watchtower/main/logo.png" width="50" height="50"> <img src="https://github.com/linuxserver/Heimdall-Apps/blob/master/WireGuard/wireguard.png" width="50" height="50"> <img src="https://raw.githubusercontent.com/linuxserver/Heimdall-Apps/master/xTeVe/xteve.png" width="50" height="50">

## How to deploy Services

To work with all the docker-composes at once I use a slightly modified version of [this docker function](https://github.com/tomMoulard/make-my-server).

```bash
#! /bin/sh

dc ()
{
    dir=$(pwd);
    cd /home/javier/homeserver;
    docker-compose $(find '${HOMESERVER_DIR}' -name 'docker-compose*.yml' -type f -printf '%p\t%d\n'  2>/dev/null | sort -n -k2 | cut -f 1 | awk '{print "-f "$0}') $@
    cd $dir;
}
```

For consistency, most of the docker images are taken from [linuxserver.io](https://www.linuxserver.io/), some of them need some additional configuration that is made through env files, in the near future I'll create neded service.env.default files to show this configuration.

## TODOs

* Add service.env.default configuration files
* Add ansible playbooks to deploy and maintain current infrastructure and services
