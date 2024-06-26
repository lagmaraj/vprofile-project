# ./Docker-files/db/Dockerfile
FROM mysql:8.0.33

LABEL Project="Vprofile"
LABEL Author="Raju"

ENV MYSQL_ROOT_PASSWORD=vprodbpass
ENV MYSQL_DATABASE=accounts

COPY db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql
