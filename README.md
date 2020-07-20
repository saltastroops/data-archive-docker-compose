# SAAO/SALT Data Archive docker compose

The SAAO/SALT Data Archive is powered by docker and is executed using docker compose.

## How to run the SAAO/SALT Data Archive

First, you must make sure that the following tools are  installed:

1. [Docker](https://www.docker.com/) and
2. [Docker compose](https://docs.docker.com/compose/)

Clone the following repositories to a location of your choice.


```sh
git clone https://github.com/saltastroops/data-archive-docker-compose.git &&
git clone https://github.com/saltastroops/data-archive-backend.git data-archive-backend &&
git clone https://github.com/saltastroops/data-archive-frontend.git
```

or using ssh

```sh
git clone git@github.com:saltastroops/data-archive-docker-compose.git &&
git clone git@github.com:saltastroops/data-archive-backend.git data-archive-backend &&
git clone git@github.com:saltastroops/data-archive-frontend.git
```

The docker compose requires the following environment variables. 

Variable | Description | Example
---- | ---- | ----
DATA_ARCHIVE_BACKEND_BASE_DIR | The location of the data archive backend | /path/to/data-archive-backend
DATA_ARCHIVE_BACKEND_PORT | Port on which the data archive backend should be listening | 4001
DATA_ARCHIVE_FRONTEND_BASE_DIR | The location of the data archive frontend | /path/to/data-archive-backend
DATA_ARCHIVE_FRONTEND_PORT | Port on which the data archive frontend should be listening | 3000
POSTGRES_IMAGE_PASSWORD | The postgres image password | secret
POSTGRES_PORT | The free port on the host to map with the postgres image port  | 5431

Execute the following command to run the data archive,

on local host

```sh
docker-compose up -d
```

on development server

```sh
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d
```

on production

```sh
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

To stop the data archive, run the following command

```sh
docker-compose down
```
