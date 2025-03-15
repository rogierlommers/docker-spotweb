# docker-spotweb

Runnign spotweb in a docker container.

Username: admin
Password: spotweb

Example docker-compose

```
services:

  spotweb:
    container_name: spotweb
    image: rogierlommers/docker-spotweb
    restart: unless-stopped
    ports:
      - 7001:80
    volumes:
      - /srv/local/services/spotweb/data:/data
      - /srv/local/services/spotweb/settings/ownsettings.php:/app/ownsettings.php
    environment:
      - TZ=Europe/Amsterdam
      - DB_ENGINE=pdo_sqlite
      - DB_NAME=/data/spotweb.db3
      - CRON_INTERVAL=*/15 * * * *
```
