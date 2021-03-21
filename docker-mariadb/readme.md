This docker-compose.yml file creates an instance of MariaDB on Alpine.
It is specifically for arm32v7 - meaning you can use it on 32bit Raspbian on a Raspberry Pi.

Make sure you replace the passwords in the yml-file with your own passwords.
You can generate strong passwords here: https://passwordsgenerator.net/

Run using:
```
docker-compose up -d
```

Many thankt to Michael Kilian for this build.
Source: https://github.com/mikilian/arm32v7-mariadb-alpine
