# Nextcloud
Nextcloud Configuration. [Documentation](https://github.com/docker-library/docs/tree/master/nextcloud)

## Configuration
The Nextcloud Docker image uses environment variables to preconfigure various settings used by the container during the build process. In this case I reference these environment variable in the file `db.env`. You will need to fill in these values for based on your own specific requirements.

As an Example:
```
MYSQL_PASSWORD=someuser
MYSQL_DATABASE=nextcloud
MYSQL_USER=someusers_password
MYSQL_ROOT_PASSWORD=root_password
NEXTCLOUD_ADMIN_USER=someotheruser
NEXTCLOUD_ADMIN_PASSWORD=someotherusers_password
NEXTCLOUD_TRUSTED_DOMAINS=nextcloud.lan
```

* `MYSQL_DATABASE`
The name of the database on the database server nextcloud will use to store data

* `MYSQL_USER`
The user nextcloud will use to access the database

* `MYSQL_PASSWORD`
The password for the user nextcloud will use to access the database

* `MYSQL_ROOT_PASSWORD`
The database root user's password; nextcloud will need this to create the database, database user, and database user's password

* `NEXTCLOUD_ADMIN_USER`
The default Administrator user that will be created for nextcloud

* `NEXTCLOUD_ADMIN_PASSWORD`
The default Administrator user's password

* `NEXTCLOUD_TRUSTED_DOMAINS`
The domains that nextcloud will connections from i.e. my local domain for my next work is `.lan` and I'll be access the nextcloud instance from the domain `nextcloud.lan`. So `nextcloud.lan` would be the trusted domain that access is allowed from. This means it would not allow access through the machines IP address or some other domain that might point to the same IP

## Build
After filling in the configuration environment variable file its time to build the docker images run:

```
docker-compose up -d
```

## Update/Upgrade
Upgrading when using docker-compose is sinmple

```
docker-compose pull
docker-compose up -d
```
