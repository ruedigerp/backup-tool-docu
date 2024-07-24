# Run BackupItAll in Docker

Erstelle die Konfigurations Dateien wir in configuration beschrieben.
Create the configuration files as described in the [configuration](/docu/configuration/).

## Dockerfile

    FROM alpine
    WORKDIR /app
    mkdir /app/enabled
    COPY etc/web /app/
    COPY bin /app/
    COPY run.sh /app/
    RUN ln -nfs /app/bin/backup.sh enabled/web

    EXEC ["/app/run.sh"]

Download [Dockerfile](/docu/Dockerfile)

## Build docker image

    docker build -t backupitall .

## Run docker container

    docker run -rm -d -it --name backupitall backupitall /bin/bash /app/run.sh

