# Order Service

Service's responsibility is to create orders.

Given service communicates with the `catalog-service` to check if pre-ordered phones exist in a database.

## Endpoints
+ `GET /api/orders` - fetch a collection of completed orders
+ `POST /api/orders` - add a new order to a database

## App requirements
+ Spring Boot 2
+ Spring Framework 5
+ JDK 10
+ Maven

