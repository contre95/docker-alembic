# Docker Alembic 
This container is intended to ease the pain of installing alembic and it's dependencies on your host in order to run alembic migrations in a Python project.

To successfully run the migrations you should have previously created the database and initialized alembic. You achieve this with the same container:

`docker container run --rm -v /path/to/dir/:/srv contre95/alembic init /srv`

The Alembic migration environment would be created on the specified path.
You would like to configure the `alembic.ini` in order to set the database connection. (Please make sure you use `127.0.0.1` instead of `localhost`)

## Run Alembic commands
To run the migration or any other alembic command simply run:

`docker container run --rm --network=host -v /alembic/migrations/env/path:/srv contre95/alembic <alembic-command>`

## Aditional Refernces
* Alembic's Documentation:  https://alembic.sqlalchemy.org/


