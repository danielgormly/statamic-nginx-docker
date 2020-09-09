# Basic Statamic & Nginx Docker Setup

**Statamic 3: See [statamic3-nginx-docker](https://github.com/danielgormly/statamic3-nginx-docker/)**

Built for a client requiring site built in Statamic. Include Statamic files in directory `statamic`.

## Installation

- Clone repository
- Download [Statamic](https://statamic.com/) and extract into `./statamic`
- Run `docker-compose up -d` to start
- Listening on port 8000
- Run statamic installer `<host>/installer.php`
- `docker-compose build` to rebuild services if you make any changes

## Files

**docker-compose.yml** Docker composition file, builds fpm & Nginx dockerfiles.

**fpm.Dockerfile** Builds from official [fpm:php-7fpm](https://hub.docker.com/_/php/) image Installs GD and required dependencies for Statamic's image manipulation capabilities. Adds `php.ini` into project (you may want to update the timezone here - defaults to `Australia/Sydney`). Makes 256mb memory available as recommended by Statamic (default for fpm:php-7fpm Docker image is 128mb).

**nginx.Dockerfile** Adds `statamic.nginx.conf` (site specific Nginx conf file) to Nginx container
