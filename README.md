# About

This is my personal docker service template repository.

# How to use

## Preliminary work

1. You can add current user to `docker` group

   ```shell
   sudo usermod -aG docker $USER
   ```

2. Create a caddy network using the following command:

   ```shell
   docker network create caddy
   ```

3. Create a wildcard certificate and private key in the `caddy/certs` directory:

   ```shell
   vim caddy/certs/certificate.pem
   vim caddy/private/key.pem
   ```

## Add a service

1. Enter a service directory:
2. Copy `.env.template` to `.env` and modify the environment variables in the `.env` file.
3. Run `docker-compose up -d` to start the service.

# Principle

1. Prefer using SQLite as the database, and use PostgreSQL if higher performance is needed.
2. Prefer saving all container data in the `data` folder under the container directory, and saving in a Docker volume if necessary.
