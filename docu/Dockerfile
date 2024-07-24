FROM alpine
WORKDIR /app
mkdir /app/enabled
COPY etc/web /app/
COPY bin /app/
COPY run.sh /app/
RUN ln -nfs /app/bin/backup.sh enabled/web

EXEC ["/app/run.sh"]