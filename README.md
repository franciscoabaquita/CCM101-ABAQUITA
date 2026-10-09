# Laboratory 06: Cloud Deployment Engineer

## Mission Overview

This laboratory introduces Infrastructure as Code with Docker Compose. The proof of concept defines a two-tier private-cloud application: Nextcloud provides the web and application tier, while MariaDB stores application data.

> **Status:** The documentation and Compose configuration described by this mission are prepared here. The KillerCoda deployment and its screenshots must be completed in the playground; no deployment evidence is included yet.

## Objectives

- Explain the roles of the web/application and database tiers.
- Describe how a Docker Compose file defines and starts related containers.
- Deploy and inspect a Nextcloud and MariaDB stack in a Linux playground.
- Document the deployment and reflect on Infrastructure as Code.

## Commands Executed

Run these commands in the KillerCoda Ubuntu playground from the project directory:

```bash
mkdir nextcloud-deployment
cd nextcloud-deployment
nano docker-compose.yml
docker-compose up -d
docker-compose ps
docker-compose down
```

The Compose YAML used for this mission is documented in [docker-compose-guide.md](docker-compose-guide.md). Save screenshots of the running containers, the Nextcloud setup page, and teardown in `screenshots/` after performing those steps.

## Skills Learned

- Describing a multi-tier application architecture.
- Reading and writing YAML configuration.
- Using Docker Compose to manage an application stack.
- Connecting containers through Compose service-name DNS.
- Documenting infrastructure procedures and deployment evidence.

## Mission Documents

- [Multi-tier architecture](multi-tier-architecture.md)
- [Docker Compose guide](docker-compose-guide.md)
- [Mission reflection](reflection.md)
