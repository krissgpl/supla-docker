# SUPLA-Docker

[![Docker Pulls](https://img.shields.io/docker/pulls/supla/supla-cloud.svg)](https://hub.docker.com/r/supla/supla-cloud/) [![Docker Build Status](https://img.shields.io/docker/build/supla/supla-cloud.svg)](https://hub.docker.com/r/supla/supla-cloud/)
 
[![Current Supla-Cloud version](https://img.shields.io/badge/SUPLA--Cloud-v2.1.6-blue.svg)](https://github.com/SUPLA/supla-cloud/releases/latest)  [![Current SUPLA-Server version](https://img.shields.io/badge/SUPLA--Server-v1.8.5-blue.svg)](https://github.com/SUPLA/supla-core/releases/latest)

Your home connected. With Docker. www.supla.org

![SUPLA-Docker](https://github.com/SUPLA/supla-docker/raw/master/supla-docker.png)

## Installation

[VIDEO](https://www.youtube.com/watch?v=MBgRUE_5dFU)

1. Install [Docker CE](https://docs.docker.com/engine/installation/) 17.06+, [docker-compose](https://docs.docker.com/compose/install/) 1.17+ and Git.
   The following _should_ work (as root):
   ```
   apt-get -y install git curl
   curl -sSL https://get.docker.com | sh
   curl -L https://github.com/docker/compose/releases/download/1.17.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
   chmod +x /usr/local/bin/docker-compose
   ```
   * if you have problems getting docker-compose into you Raspberry Pi, try an alternative method:
     ```
     apt-get -y install python-pip && pip install docker-compose
     ```
1. Clone this repository.
   ```
   git clone https://github.com/SUPLA/supla-docker.git
   ```
1. Generate sample config by running
   ```
   ./supla-docker/supla.sh
   ```
   Review the settings in `./supla-docker/.env` file.
1. Start SUPLA!
   ```
   ./supla-docker/supla.sh start
   ```
   
## Creating an user account
Before you launch the containers, set the `FIRST_USER_EMAIL` and `FIRST_USER_PASSWORD` settings in the `.env` file. 
The account will be automatically created for you. You can remove these settings afterwards not to expose your password.

If the containers are started already, you can create new user account interactively with:
```
./supla-docker/supla.sh create-confirmed-user
```

## Upgrading to the newest version
```
cd supla-docker
git pull
./supla.sh upgrade
```
