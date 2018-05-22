# Phone catalog application

Simple application based on microservices architecture which runs in docker container.

+ catalog-service (to store phone data and retrieve available phones)
+ order-service (to add new orders and retrieve completed orders)

Each service handles it's own database (containerized MongoDB).
## Relationship

**order-service** uses **catalog-service** to verify if phones are available and to retrieve phone metadata (name, price)


## App requirements
+ Spring Boot 2
+ Spring Framework 5
+ JDK 10
+ Maven

## How to run
```
// build services jars
$ mvn clean package 

// bootstrap and run docker containers
$ docker-compose up 
```

## Questions
Q1. How would you improve the system?
+ To prevent a database from being accessed directly via API on each request we can add a cache mechanism. It will reduce a load on a database server and improve response time.

Q2. How would you avoid your order API to be overflow?
+ To prevent an API from being overwhelmed we can add a backpressure mechanism provided by reactive nature of Spring WebFlux (as an implementation of Reactive Streams Manifesto).