# Online Clinic Management System

Online Clinic Management System (OCMS) is a web application that allows you to manage your clinic. This application offers you insight on your clinic activity and keeps historical records of every single patient, all his visits and related prescriptions. The patients info you can store include tobacco usage, alcohol intake, surgical and obstetric history and genetic diseases. It’s easy to use, and makes you become more organized and accordingly, more productive. 

License: MIT License

Requires PHP and MySQL

# Docker: PHP & MySQL

This is a docker installion of OCMS. The original files can be downloaded from this [Link](https://bigprof.com/appgini/applications/online-clinic-management-system)

The objective of this repo is to have available an easy way to deploy the app for testing purposes (test automation practice for example).

This project offers an easy installation with standard versions and the minimal amount of mods of the docker images. It comes with `PHP 7.3` y `MySQL 5.7`.

## Requirements

* [Docker Desktop](https://www.docker.com/products/docker-desktop)

## Environment configuration

You could use the default configuration that comes within the repo and the app will work, however, sometimes it is recommended the modification of the configuration depending on the needs. To do so, please go to the `.env` and edit the following options:

* `PHP_VERSION` PHP version ([Available versions of PHP](https://github.com/docker-library/docs/blob/master/php/README.md#supported-tags-and-respective-dockerfile-links)).
* `PHP_PORT` Web Server Port.
* `MYSQL_VERSION` MySQL version([available versions of MySQL](https://hub.docker.com/_/mysql)).
* `MYSQL_USER` username to connect to MySQL.
* `MYSQL_PASSWORD` password to connect to MySQL.
* `MYSQL_DATABASE` database name created by default when the docker compose command is run.

## How to install the environment

It is done through the command line:

```zsh
docker-compose up -d
```

You can verify the installation is correct by navigating to [http://localhost/info.php](http://localhost/info.php)

## Available commands

Once installed, you could use the following commands:

```zsh
docker-compose start    # Start the app.
docker-compose stop     # Stop the app.
docker-compose down     # Stop and delete the app
```

## Filesystem Structure


* `/docker/` contains the docker configuration files.
* `/www/clinic` contains the OCMS source files.

## Access

### Web

* Once the system is up, navigate to http://localhost/clinic

### Database

There's two domains to connect to the DB

* `mysql`: to connect from PHP files. This is also used in the configuration file as the DB Server of the OCMS app.
* `localhost`: for external connections to the container.

Default credentials for the DB connections are:

| User | Password | Database |
|:---:|:---:|:---:|
| clinic | clinic | clinic |

Default credentials to access OCMS:

| User | Password |
|:---:|:---:|
| admin | admin |


Credits: The PHP and MySQL base docker project required to run the OCMS app was taken from this [repo](https://github.com/kodetop/docker-php-mysql).
