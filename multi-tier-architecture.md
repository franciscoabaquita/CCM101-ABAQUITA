# Two-Tier Architecture

A two-tier architecture divides an application into two cooperating layers: a web/application tier and a database tier. In this mission, Nextcloud is the first tier and MariaDB is the second.

## The Web/Application Tier

The Nextcloud container serves the web interface and handles HTTP requests from users. It also runs the application logic that uses the database to manage accounts, settings, and file metadata.

## The Database Tier

The MariaDB container stores persistent relational data used by Nextcloud, such as user accounts and file metadata. The application connects to it using the database name, username, and password supplied through environment variables.

## Why Separate Them?

Keeping the application and database in separate containers gives each tier a clear responsibility and lets engineers update, monitor, or scale them independently. It also makes the deployment easier to reproduce and avoids coupling the database lifecycle to the web application process.
