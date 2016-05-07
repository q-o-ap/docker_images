# postgresql-docker

Docker image for PostgreSQL

**Get it running:**

``$ docker-compose up``

**Testing the running PostgreSQL**

To test the running container we can use any client, even the commandline one:


``psql -h localhost -p 5432 -U pguser -W pgdb``

When you are prompted for password, type: pguser

_Please note that localhost is only valid if you are running Docker on Ubuntu. If you are an OSX user, you need to discover the correct ip using: boot2docker ip_

docker run -d -p 5432:5432 -v ~/development/docker/tradeData/postgresData/:/var/lib/postgresql/9.5/main --name pg95_2 dv_pg95

2016-05-05 11:09:09 UTC [1-2] FATAL:  data directory "/var/lib/postgresql/9.5/main" has wrong ownership
2016-05-05 11:09:09 UTC [1-3] HINT:  The server must be started by the user that owns the data directory.
