# Doecker Cheat Sheet

This is a docker cheat sheet for everyone to use. Feel free to clone it or either use it for any usage.
You can contibute with me to grow the cheat sheet for anyone who wants to start using a container ASAP.
Of course, It's not a full docker documentation so you may want to refer to original repositories on hub.docker.com.

## CONTAINERS

###### kill all running containers

```
docker kill $(docker ps -q)
```

###### delete all stopped docker containers

```
docker rm $(docker ps -a -q)
```

## IMAGES 

###### remove a docker image

```
docker rmi <image name>
```

###### delete untagged images

```
docker rmi $(docker images -f dangling=true)
```

###### delete all images

```
docker rmi $(docker images -q)
```

## VOLUMES

###### remove all dangling volumes

```
docker volume prune
```

## RUNNING

###### PostgreSQL Commands
>Running On Default Mode

```
docker run --name todo-postgres -v c:\Users\ehsan\Desktop\postgres -e POSTGRES_PASSWORD=postgres -p 5432:5432 -d postgres
```

>Running With Custom Directory

```
docker run --name postgres -e POSTGRES_PASSWORD=postgres -e PGDATA=/var/lib/postgresql/data/pgdata -v c:/users/ehsan/desktop/postgres:/var/lib/postgresql/data -p 7070:5432 -d postgres
```

###### MongoDB Commands

>Running on Default Mode

```
docker run --name mongo -p 27017:27017 -d mongo 
```
