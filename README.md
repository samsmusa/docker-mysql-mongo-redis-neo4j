# docker-mysql-mongo-redis

* Run MySQL, MongoDB, Neo4j, and Redis in docker

* The project can used in development environment

* **Do not use in production environment**

## Prerequisites

* [docker](https://docs.docker.com/install/)
* [Git](https://git-scm.com/)

## Installing

git clone the project

```shell
git clone https://github.com/samsmusa/docker-mysql-mongo-redis-neo4j.git
```

## Running

```shell
cd docker-mysql-mongo-redis
docker compose up -d

# show docker-compose log
docker compose logs -f
```

## Show docker container
```shell
docker ps -a
```
## Show specific container network ip
```shell
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container name>
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' docker-mysql-mongo-redis-neo4j-mongo-1
```

## Build connection with ssh(mysql)
first run
```shell
sudo apt install mysql-client -y
```
then
```shell
mysql -h 127.0.0.1 -P 3306 --protocol=tcp -u user -p
```

## Access Bash
```shell
docker exec -it <container name> bash
docker exec -it docker-mysql-mongo-redis-neo4j-mysql-1 bash
```
## Mongo Compass access
```shell
mongodb://<local-ip>:27017/
```

## Redis cli access
```shell
docker exec -it docker-mysql-mongo-redis-neo4j-redis-1 bash
>>>redis-cli
>>>ping
```

## Databases username and password

| database | username | password |
| :------: | :------: | :------: |
|  mysql   |   root   |   root   |
|  mongo   |    /     |    /     |
|  redis   |    /     |    /     |
|  neo4j   |    /     |    /     |

