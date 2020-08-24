## MariaDB

Before bring container up, please change environment variables at docker-compose.yaml

```
MYSQL_ROOT_PASSWORD: xxxxx
MYSQL_USER: xxxx
MYSQL_DATABASE: xxxx
MYSQL_PASSWORD: xxxx
```

Create two folder to store database locally

```bash
mkdir data_dev
mkdir data_prod
```

## Port

MariaDB will expose port 6033 you can change it at docker-compose.yaml

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
