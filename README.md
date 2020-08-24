![Docker](https://github.com/wborbajr/docker_mysql/blob/master/docker.jpeg)

## Downloading

```bash
git clone https://github.com/wborbajr/docker_mysql.git
cd docker_mysql
```

## MariaDB

Before bring container up, please change environment variables at **docker-compose.yaml**

```
MYSQL_ROOT_PASSWORD: xxxxx
MYSQL_USER: xxxx
MYSQL_DATABASE: xxxx
MYSQL_PASSWORD: xxxx
```

## Database

All databases will be saved locally at data folder.

Create two folders inside **docker_mysql**, to store **_development_** and **_production_** database locally.

**_PS_** If you decided to change folders name or path, please, remember to modify the entry **volumes** at **docker-compose.yaml**

```
volumes:
    - ./data_prod:/var/lib/mysql:rw
```

```bash
mkdir data_dev
mkdir data_prod
```

## Port

MariaDB will expose port **60330** for development environment and **60331** for production environment.
You can change it at **docker-compose.yaml** for your own propose.

## To execute

### Development

```bash
docker-compose -f docker-compose-dev.yaml up -d
```

### Production

```bash
docker-compose -f docker-compose-prod.yaml up -d
```

## To stop

### Stopping Development environment

```bash
docker-compose -f docker-compose-dev.yaml down
```

### Stopping Production environment

```bash
docker-compose -f docker-compose-prod.yaml down
```

## Configuration

You can setup your own configurations just changing file **my.conf** located at config folder.

After setup your own MariaDB configuration, don't forget to enable at **docker-compose.yaml** at **volumes** section to read your configuration file, removing comment tag.

## Checking status

```bash
docker-compose -f docker-compose-dev.yaml ps
or
docker-compose -f docker-compose-prod.yaml ps
```
