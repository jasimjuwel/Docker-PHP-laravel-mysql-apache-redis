## About Project

Dockerize PHP Apache Laravel Mysql Redis 

## Technologies
- PHP 7.2.5
- Laravel 7
- Mysql 8
- Docker
- Redis

## Docker Instruction:

* Docker is available in this project. Please install Docker before start. Click [here](https://www.docker.com/) to know about Docker. For installation guide please follow [this](https://www.docker.com/get-started) link.*

## Clone the docker files
- git clone https://github.dev/jasimjuwel/Docker-PHP-laravel-mysql-apache.git
- put this docker files into laravel project
- cp .env.example .env
## Configure .env
    >  vim .env

        APP_NAME=testapp
        DB_CONNECTION=mysql
        DB_HOST=149.23.0.2
        DB_PORT=3306
        DB_DATABASE=test_app_db
        DB_USERNAME=testapp_user
        DB_PASSWORD=123456
        TZ=Asia/Dhaka
- 
        CACHE_DRIVER=redis
- 
        REDIS_CLIENT=predis
        REDIS_HOST=149.23.0.5
        REDIS_PASSWORD=null
        REDIS_PORT=6379
- 
        UID=1000

## Docker compose
- docker-compose up --build
- docker-compose up --build -d
- docker-compose down -v

## Basic Laravel and NPM command
- docker exec -ti -u duser testapp-app bash
- chmod -R 775 storage
- chmod 755 storage bootstrap/cache
- php artisan config:clear
- php artisan cache:clear
- php artisan cache:clear
- php artisan migrate
- npm install

## Configure mySql
- docker exec -ti testapp-db bash
- mysql -u root -p root

## Configure redis
- `docker exec -ti testapp-redis  /bin/sh`
- `redis-cli`
- `ping`

## virtual domain adding
- edit `vim /etc/hosts`
- then add this line `149.23.0.4 testapp.dev` for browsing using domain name
-
## Run app
- http://149.23.0.4/
- http://testapp.dev/

## Run phpmyadmin
- http://149.23.0.3

## notes
- Feel free inform me for any help. email : jasimjuwel0@gmail.com