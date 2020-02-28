# DS4WP
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

A docker stack made for wordpress based on :

- Wordpress:5-php7.4-fpm
- nginx (latest)
- mariadb (latest)
- phpMyAdmin (latest)
- wodby/varnish (latest)
- Traefik (latest from wodby/varnish)
- HTTPS TLS autogen certificat 

## Details
This docker-compose stack is meant to be used to create a complete WordPress stack cached by varnish and routed through Traefik V2 via dynamics labels.
This stack includes HTTPS autogen certificate thanks to Traefik !

Some useful WordPress plugins are already included in this release but will need to be activated manually if you want them. 

If you are willing to run multiple websites (and so multiple stacks) on a single host you will need to comment the Traefik service from the docker-compose file and implement a Traefik out-of-the-box in order to prevent reserved ports **(repo will be provided later)**.

## Environment variables

You are supposed to change variables in .env file according to your needs

| VARIABLE | USAGE |
| ------ | ------ |
| PROJECT_NAME | project name that will be used as base of containers name |
| PROJECT_BASE_URL | Domain name of your website **without leading www** (eg: mywebsite.com) |
| CERTMAIL | Contact email for HTTPS certificat request|
| DB_NAME | Name of the WordPress database to create on MariaDB|
| TABLE_PREFIX | Prefix of the WordPress tables to create on MariaDB **(change it for security reason)**|
| DB_USER |Username WordPress will use to connect to MariaDB **(change it for security reason)** |
| DB_PASSWORD | Password WordPress will use to connect to MariaDB **(change it for security reason)** |
| DB_ROOT_PASSWORD | Root password of MariaDB installation **(change it for security reason)**|
