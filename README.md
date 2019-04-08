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
