# laravel_docker_workspace
## Overview
docker-compose.yml for Laravel

## Description
- Laravel latest
- MySQL 5.7
- Nginx latest
- PHP-FPM latest

## Usage
### MySQL setting
```sh
$ vim docker-compose.yml
```

```yml
# mysql block
environment:
  MYSQL_DATABASE: <your-db-name>(default: laravel_db)
  MYSQL_USER: <user-name>(default: user)
  MYSQL_PASSWORD: <your-password>(default: password)
  MYSQL_ROOT_PASSWORD: <your-password>(default: password)
```
### Download and create container
```sh
$ docker-compose up -d
```

### Create Laravel project
```sh
$ docker-compose exec app bash
```
```sh
$ composer create-project --prefer-dist laravel/laravel <your-project-name>
$ exit
```

### Nginx setting
```sh
$ vim ./docker/nginx_conf/default.conf
```

```nginx
root  /var/www/html/<your-project-name>/public;
```

```sh
$ docker-compose restart
```

### .env setting
```sh
$ vim ./document_root/<your-project-name>/.env
```

```
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=<your-db-name>(default: laravel_db)
DB_USERNAME=<user-name>(default: user)
DB_PASSWORD=<your-password>(default: password)
```
