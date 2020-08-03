# Nextcloud
Nextcloud Configuration

## Configuration
In the `db.env` file you will need to fill in the values for the environment variables that will be used by docker

As an Example:
```
MYSQL_PASSWORD=someuser
MYSQL_DATABASE=nextcloud
MYSQL_USER=someusers_password
MYSQL_ROOT_PASSWORD=root_password
```

After that its time to build the docker images run:

```
docker-compose up -d
```
