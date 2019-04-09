[My Docker Hub](https://hub.docker.com/u/somkiat)

[![Build Status](https://travis-ci.com/up1/workshop-depoy-microservice-java.svg?branch=master)](https://travis-ci.com/up1/workshop-depoy-microservice-java)

[My catalog service in Google Cloud](http://<ip>:<port>/catalog/1)

# Demo :: Deploy microservices with Docker

## Step 1 :: Clone project
```
$git clone https://github.com/up1/workshop-depoy-microservice-java.git
$cd workshop-depoy-microservice-java
#ls

README.md catalog   product
```

## Step 2 :: Build image of catalog service
```
$cd catalog
$docker image build -t catalog_service:1.0 .
$docker image ls
```

## Step 3 :: Build image of product service
```
$cd product
$docker image build -t product_service:1.0 .
$docker image ls
```

## Step 4 :: Push image to Container Image Registry (https://hub.docker.com/)
```
$docker login
Login Succeeded

$docker image tag catalog_service:1.0 <username>/catalog_service:1.0
$docker image push <username>/catalog_service:1.0

$docker image tag product_service:1.0 <username>/product_service:1.0
$docker image push <username>/product_service:1.0
```

## Step 5 :: Deploy container with Docker compose
```
$cd ..
$docker-compose up -d
$docker-compose ps
                   Name                             Command             State              Ports
--------------------------------------------------------------------------------------------------------
workshop-depoy-microservice-java_catalog_1   java -jar catalog.jar   Up (healthy)   0.0.0.0:80->8080/tcp
workshop-depoy-microservice-java_product_1   java -jar product.jar   Up (healthy)
```
