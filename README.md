# Docker LAMP

This repository contains a docker LAMP environment that you can configure according to your needs.

## Installation

Clone the repository:

```
git clone https://github.com/corentinmagique/lamp-docker.git
```

## Usage 

Configure .env file :

```
#GENERAL 
PROJECT_NAME=LAMP #Project name 
PHPVERSION=php81 #Php version, at the moment only php81 is supported.
DATABASE=mariadblatest #Possible values : mariadblatest or mysqllatest
TIMEZONE=Europe/Paris #Your timezone

MYSQL_ROOT_PASSWORD=0000 #Database root password
MYSQL_DATABASE=docker #Database name
MYSQL_USER=root #Database user
MYSQL_PASSWORD=docker #Database password
MYSQL_TCP_PORT=52000 #Database port

WEBSERVER_PORT=5501 #Server port
PMA_PORT=8081 #Phpmyadmin port
```