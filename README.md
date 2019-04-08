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
$docker-compose up -d
$docker-compose ps
```
