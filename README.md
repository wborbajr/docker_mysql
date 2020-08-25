![Docker](https://github.com/wborbajr/docker_mysql/blob/master/docker.jpeg)

## Downloading

```bash
git clone https://github.com/wborbajr/docker_mysql.git
cd docker_mysql
```

## MariaDB

Before bring container up, please change environment settings at **.env**

```
MYSQL_ROOT_PASSWORD: xxxxx
MYSQL_USER: xxxx
MYSQL_DATABASE: xxxx
MYSQL_PASSWORD: xxxx
```

## Database

All databases will be saved locally at data folder **./data/mysql**

**PS:** If you decided to change folders name or path, please, remember to modify the entry **volumes** at **docker-compose.yaml**

```
volumes:
    - ./data/mysql:/var/lib/mysql:rw
```

## Port

MariaDB will expose port **6033**, so remember to configure your MySQL Client to connect at **_Port: 6033_**

You can change it at **docker-compose.yaml** for your own propose.

## To execute

### Just MariaDB

```bash
docker-compose up -d database
```

Or you can run using Makefile

```bash
make up-db
```

### Bringing up MariaDB and Adminer

```bash
docker-compose up -d
```

Or you can run using Makefile

```bash
make up-all
```

## To stop

### Stopping Development environment

```bash
docker-compose down
```

Or you can run using Makefile

```bash
make down
```

## Configuration

You can setup your own configurations just changing file **my.conf** located at config folder.

After setup your own MariaDB configuration, don't forget to enable at **docker-compose.yaml** at **volumes** section to read your configuration file, removing comment tag.

Alternatively you can setup an initial database to be created just modifying **init.sql** that it is at **initdb** folder and enabling at **docker-compose.yaml** at **volumes** section.

## Checking status

```bash
docker-compose ps
```
