# PostgreSQL

## Execute commands as postgres user

`su postgres` - switch user

or

`-U postgres` - argument to define user in console utilities

or

`docker exec -it -u postgres <container_name> bash` - attach console to container using specified user

## Create database

```createdb <db_name>```

## Drop database

```dropdb -f <db_name>```

`-f` stands for force drop

## Dump database

```pg_dump <db_name> > /path/to/dump`date +%Y-%m-%d_%H-%M`.sql```

## Restore database from dump

```psql -d <db_name> < /path/to/dump.sql```

## Dump remote database from docker container and transfer the dump to a local machine

```
ssh <user>@<ip> "docker exec -t <container_name> pg_dump <db_name> -U postgres | gzip -9" | gzip -d > /path/to/dump_`date +%Y-%m-%d_%H-%M`.sql
```
