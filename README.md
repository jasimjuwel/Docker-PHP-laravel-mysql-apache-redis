
## Docker Instruction:
*  `Set UID in .env`

        UID=1000


## Ports
- php 8060
- mysql 3305
- phpmyadmin 8070

## Folder Permission

- chmod -R 775 storage
- chmod 755 storage bootstrap/cache

## Basic Laravel and NPM command

- docker exec -ti -u duser pureit_app_1 bash
- npm install
- npm run watch
- php artisan config:clear
- php artisan cache:clear
- php artisan cache:clear
- php artisan migrate
## Configure mySql

- docker exec -ti pureit_db_1 bash
- mysql -u root -p
- ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY 'root';
- docker inspect 3d226681d8d2

## Docker compose
- docker-compose up --build
- docker exec -ti -u duser laravel-docker_app_1 bash

- docker-compose down -v
- docker-compose up --build -d
- docker-compose exec app php artisan config:cache
- docker-compose exec app ls -l

## Run app
- http://localhost:8060/

## Note:

I tried to follow the best practices, but any suggestion, modification is highly appreciated.
