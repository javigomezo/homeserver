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

## How to deploy Services

TO-DO

```bash
#! /bin/sh

```

For consistency, most of the docker images are taken from [linuxserver.io](https://www.linuxserver.io/).

## TODOs

* ~~Add ansible playbooks to deploy and maintain current infrastructure and services~~
* Improve readme
