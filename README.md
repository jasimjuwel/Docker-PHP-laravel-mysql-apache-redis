## Docker Instruction:
*  `Set UID and APP_NAME in .env`
   APP_NAME=testapp
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
