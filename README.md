# Doecker Cheat Sheet

This is a docker cheat sheet for everyone to use. Feel free to clone it or either use it for any usage.
You can contibute with me to grow the cheat sheet for anyone who wants to start using a container ASAP.
Of course, It's not a full docker documentation so you may want to refer to original repositories on hub.docker.com.

## CONTAINERS

###### Show a list of all running containers

```
docker ps
```

###### Show a list of all containers

```
docker ps -a
```

###### Running a container

```
docker run <CONTAINER>
```

###### Stopping a container

```
docker stop <CONTAINER>
```

###### kill all running containers

```
docker kill $(docker ps -q)
```

###### delete all stopped docker containers

```
docker rm $(docker ps -a -q)
```

###### Removing a specific container

```
docker rm <CONTAINER>
```

## IMAGES 

###### Show a list of all images

```
docker images
```

###### Show a list of dangling images

```
docker images prune
```

###### Saving an image into .Tar file

```
docker save <IMAGE> > <IMAGE.TAR>
```
>Example
```
docker save nginx > nginx.tar
```

###### Loading from an image file

```
docker load -i <TAR FILE>
```

###### remove a docker image

```
docker rmi <image name>
```

###### Delete untagged images

```
docker rmi $(docker images -f dangling=true)
```

###### Delete all images

```
docker rmi $(docker images -q)
```

## VOLUMES

###### Remove all dangling volumes

```
docker volume prune
```

## RUNNING

###### PostgreSQL Commands
>Running On Default Mode

```
docker run --name todo-postgres -e POSTGRES_PASSWORD=postgres -p 5432:5432 -d postgres
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

###### MySQL Commands

>Running on Default Mode and `tag` is the version you want

```
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag
```

###### SQL Server Commands

>Running on Default mode but specify the version based on image name

```
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=yourStrong(!)Password' -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-CU8-ubuntu
```

###### RabbitMQ Commands

>Running on Default mode

```
docker run -d --hostname my-rabbit -p 5672:5672 --name some-rabbit rabbitmq:3
```
