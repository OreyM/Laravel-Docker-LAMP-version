# DOCKER
down:
	docker-compose down

build-visible:
	docker-compose up --build

build:
	docker-compose up --build -d

up:
	docker-compose up -d


# CONTAINER
bash:
	docker-compose exec php-cli bash

db: #pass=user
	mysql -u orey -p --port 33061 --host 127.0.0.1 

# LARAVEL
perm:
	sudo chown ${USER}:${USER} www/bootstrap/cache -R
	sudo chown ${USER}:${USER} www/storage -R
	sudo chown ${USER}:${USER} www/app -R
	if [ -d "www/node_modules" ]; then sudo chown ${USER}:${USER} www/node_modules -R; fi
	if [ -d "www/public/build" ]; then sudo chown ${USER}:${USER} www/public/build -R; fi

perm-cache:
	sudo chmod 777 -R www/storage && sudo chmod 777 -R www/bootstrap/cache

perm-app:
	sudo chown ${USER}:${USER} www/app -R

perm-node:
	if [ -d "www/node_modules" ]; then sudo chown ${USER}:${USER} www/node_modules -R; fi
	if [ -d "www/public/build" ]; then sudo chown ${USER}:${USER} www/public/build -R; fi

testy:
	docker-compose exec php-cli vendor/bin/phpunit --colors=always

route:
	docker-compose exec php-cli php artisan route:list

refresh:
	docker-compose exec php-cli php artisan migrate:fresh --seed

#NODE
modules-install:
	docker exec -it dev_node_1 yarn install

run-dev:
	docker exec -it dev_node_1 yarn run dev

run-prod:
	docker exec -it dev_node_1 yarn run prod

watch:
	docker exec -it dev_node_1 yarn run watch