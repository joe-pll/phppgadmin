phpPgAdmin Docker
=================

## What is phpPgAdmin?
phpPgAdmin is a web-based administration tool for PostgreSQL. It is perfect for PostgreSQL DBAs, newbies, and hosting services.

## How to run the docker container
To run a docker container with the image, execute:  
```bash
docker run -d --name phppgadmin --link postgres:postgres -p 8060:8060 tadaweb/phppgadmin
```

## Environment variables
| Variable        | default  | description  |
| --------------  | -------- | ------------ |
| PHPPGADMIN_PORT | 8060       | The port on which the lighttpd server must listen |
| POSTGRESQL_DEFAULT_DB | defaultdb | The default connection db for the postgresql |
| POSTGRESQL_HOSTS | localhost:5432 | A comma separated list of PostgreSql hosts. If the port it is not specified it will be replaced by 5432. |

## Examples
```bash
docker run -d --name phppgadmin -e "POSTGRESQL_HOSTS=postgresql1.local:5444,postgresql2.local" \
           -e "PHPPGADMIN_PORT=8111" -p 8060:8111 tadaweb/phpphadmin
```
