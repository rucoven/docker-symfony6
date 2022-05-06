## Install project

``docker-compose up -f docker/docker-compose.yml -d --build``

## import database :

``
docker exec -i alltricks-database mysql -u root -psecret symfony_docker < data/fixtures.sql
``

## lanch test
`` ------------------------------ ``

## EntryPoint

[Liste des articles](http://)
