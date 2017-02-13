# Fireguard Docker Containers


# Commands

## Info for Docker Machine
docker info

## Up containers do docker-compose
docker-compose up

## Finish containers
docker-compose down

## Stop containers
docker-compose stop

## Start containers
docker-compose start

## Execute in containers  
docker-compose exec web bash

## List all images
docker images

## Builder for custom container 
docker-compose build

## Delete image_name
docker rmi image_name

## Delete all docker containers
docker rm $(docker ps -a -q)

## Delete all docker images
docker rmi $(docker images -q)


## Create image for containers
docker build -t fireguard/php-nginx ./containers/php-nginx/7.1/

## Clear not usage images
docker rmi $(docker images --filter "dangling=true" -q --no-trunc)

## Send image
docker login
docker tag 4f4249d82004 fireguard/php-nginx:7.1
docker push fireguard/php-nginx
