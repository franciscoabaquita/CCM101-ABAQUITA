# Docker Compose Guide

This guide explains the Compose configuration for the Nextcloud and MariaDB proof of concept. Create `docker-compose.yml` in the `nextcloud-deployment` directory in the KillerCoda playground and enter:

```yaml
version: '3'

services:
  database:
    image: mariadb:10.6
    environment:
      - MYSQL_ROOT_PASSWORD=cloudnova_root
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user

  app:
    image: nextcloud
    ports:
      - 8080:80
    environment:
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user
      - MYSQL_HOST=database
```

## The `services:` Block

The `services:` block declares the containers that make up the application. This file defines `database`, using the MariaDB 10.6 image, and `app`, using the Nextcloud image. Compose creates a private network for the project so the services can communicate.

## How Nextcloud Finds MariaDB

`MYSQL_HOST=database` tells the Nextcloud container to connect to the Compose service named `database`. Compose provides DNS for service names on its project network, so the application can use that name as the database host without needing a manually assigned container IP address.

## `docker run` Compared with `docker-compose up -d`

`docker run` starts an individual container using options supplied on the command line. `docker-compose up -d` reads the YAML file and creates or starts all the declared services and their shared networking, then returns while they run in the background. The configuration can be reused to recreate the stack, while `docker-compose ps` lists its containers and `docker-compose down` stops and removes them.

## Deployment Commands

Run these commands in the directory containing `docker-compose.yml`:

```bash
docker-compose up -d
docker-compose ps
docker-compose down
```

The lab's sample passwords are plaintext demonstration values and should not be used for a real deployment. Production credentials should be strong, kept out of source control, and supplied through an appropriate secrets-management mechanism.
