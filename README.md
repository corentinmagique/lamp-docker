# Docker LAMP

This repository contains a docker LAMP environment that you can configure according to your needs. At the moment, it consists in : 

- PHP
- Apache
- MySQL / MariaDB
- phpMyAdmin

At the moment, there is one PHP version :

- 8.1.x

## Installation

- Clone the repository :

```
git clone https://github.com/corentinmagique/lamp-docker.git
```

- Configure `.env file` :

```
PROJECT_NAME=LAMP #Project name 
PHPVERSION=php81 #Php version, at the moment only php81 is supported.
DATABASE=mariadblatest #Possible values : mariadblatest or mysqllatest
TIMEZONE=Europe/Paris #Your timezone

MYSQL_ROOT_PASSWORD=0000 #Database root password
MYSQL_DATABASE=docker #Database name
MYSQL_USER=root #Database user
MYSQL_PASSWORD=docker #Database passwords
MYSQL_TCP_PORT=52000 #Database port

WEBSERVER_PORT=5501 #Server port
PMA_PORT=8081 #Phpmyadmin port
```
- Configure `config/php/php.ini` && `config/vhost/default.conf`

- Then run : 
```
docker-compose up -d
```

### PHP Extensions

At the moment : 

- pdo_mysql
- exif

You can add more in the corresponding `Dockerfile` (file in `bin/phpX.X/`) : 

```
RUN docker-php-ext-install pdo_mysql && \
    docker-php-ext-install exif 
```

### Cron

If you need crons, configure `cron` file and run (in the webserver shell) :

```
crontab /etc/cron.d/cron && service cron start
```

