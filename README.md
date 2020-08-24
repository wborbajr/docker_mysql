![Docker](https://github.com/wborbajr/docker_mysql/blob/master/docker.jpeg)

## MariaDB

Before bring container up, please change environment variables at docker-compose.yaml

```
MYSQL_ROOT_PASSWORD: xxxxx
MYSQL_USER: xxxx
MYSQL_DATABASE: xxxx
MYSQL_PASSWORD: xxxx
```

Create two folder to store development and production database locally

```bash
mkdir data_dev
mkdir data_prod
```

## Port

MariaDB will expose port 60330 for development environment and 60331 for production environment.
You can change it at docker-compose.yaml for your own propose.

## To execute

```bash
docker-compose up -d
```

# To stop

```bash
docker-compose down
```

## Database

All databases will be saved locally at data folder.

## Configuration

You can setup your own configurations just changing file my.conf that is at config folder

## Checking status

```bash
docker-compose ps
```
