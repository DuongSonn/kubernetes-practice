# Local App

## Postgres

- Deployment: kubectl create -f postgres/deployment.yml
- Service: kubectl create -f postgres/service.yml

## Pgadmin

- Deployment: kubectl create -f pgadmin/deployment.yml
- Service: kubectl create -f pgadmin/service.yml

## Redis

- Deployment: kubectl create -f redis/deployment.yml
- Service: kubectl create -f redis/service.yml

## kafka

- Deployment: kubectl create -f kafka/deployment.yml
- Service: kubectl create -f kafka/service.yml

## Krakend

- Deployment
  - Generate docker image: docker build -t `custom-krakend`:`v1` .
  - Deployment: kubectl create -f krakend/deployment.yml
  - Service: kubectl create -f krakend/service.yml
