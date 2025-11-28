# PostgreSQL

## Execute commands as postgres user

`su postgres` - switch user

or

`-U postgres` - argument to define user in console utilities

or

`docker exec -it -u postgres <container_name> bash` - attach console to container using specified user

## Create database

```createdb <db>```

## Drop database

```dropdb -f <db>```

`-f` stands for force drop

Recreate the database running in Docker container:

```docker compose exec -it <service> bash -c "dropdb -f -U <user> <db>; createdb -U <user> <db>"```

```docker exec -it <container> bash -c "dropdb -f -U <user> <db>; createdb -U <user> <db>"```

## Dump database

```pg_dump <db> > /path/to/dump`date +%Y-%m-%d_%H-%M`.sql```

## Restore database from dump

```psql -d <db> < /path/to/dump.sql```

From a TAR file:

```pg_restore -c -U <user> -d <db> /path/to/file.tar```

> `-c` is for `--clean`, DROP all the objects that will be restored

## Dump remote database from docker container and transfer the dump to a local machine

```
ssh <user>@<ip> "docker exec -t <container_name> pg_dump <db> -U postgres | gzip -9" | gzip -d > /path/to/dump_`date +%Y-%m-%d_%H-%M`.sql
```
