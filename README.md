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