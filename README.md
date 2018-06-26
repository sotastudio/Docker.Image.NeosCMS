# Neos CMS Docker Images

Just a kickstart repo to get things started quickly. Images are build on debian stretch slim.

## Usage

**Create database container**

```
$ docker run -d --name neos-db \
    -e MYSQL_ROOT_PASSWORD=yourrootpassword \
    -e MYSQL_USER=neos \
    -e MYSQL_PASSWORD=yourpassword \
    -e MYSQL_DATABASE=neos \
    mariadb:latest \
    --character-set-server=utf8 \
    --collation-server=utf8_unicode_ci
```

**Create web container**

```
$ docker run -d --name neos-web \
    --link neos-db:db \
    -p 80:80 \
    sotastudio/neoscms:4
```

**Get started**

Call localhost and setup the CMS. Use above defined database container name instead of localhost or 127.0.0.1.