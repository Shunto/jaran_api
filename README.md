#jaran\_api


##Docker

Download Docker on your Mac. : https://hub.docker.com/editions/community/docker-ce-desktop-mac 
Open Docker.


##Setup

```
$ docker-compose up
$ docker exec -i $(docker ps | grep postgres | awk '{print $1}') psql -U postgres -d postgres < db_data.sql
```

When you shut down jaran\_api

```
$ docker-compose down
```


##Usage

open url : http://localhost:8000/jaran\_onsen


##Backup and restore database

Back up

```
$ docker exec $(docker ps | grep postgres | awk '{print $1}') pg_dump -U postgres postgres > db_data.sql
```

Restore
```
$ docker exec -i $(docker ps | grep postgres | awk '{print $1}') psql -U postgres -d postgres < db_data.sql
```