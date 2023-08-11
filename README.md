# Spring Cloud 2022 Project Documentation

## Projects

* Main documentation (this project) - https://github.com/pluralsight-springcloud2022/project-docs
* Spring Cloud Gateway API Gateway - https://github.com/pluralsight-springcloud2022/api-gateway
* Spring Cloud Netflix Eureka Server - https://github.com/pluralsight-springcloud2022/eureka-service-registry
* Customer Service - https://github.com/pluralsight-springcloud2022/customer-service
* Order Service - https://github.com/pluralsight-springcloud2022/order-service

## Execution

To test the full system:

### Start the Eureka Service Registry

Run the following command to start the service registry:

```
.\mvnw spring-boot:run
```

### Start the Customer and Order Services

Run the following command to start each service with the default port:

```
.\mvnw spring-boot:run
```

You should now be able to access endpoints below:

```
http://localhost:8000/api/v1/customers/1
http://localhost:8001/api/v1/orders/1
```

Then, run the command again to start an additional service on a different port:

```
.\mvnw spring-boot:run -D'spring-boot.run.jvmArguments="-Dserver.port=XXXX"'
```

### Start the API Gateway

Run the following command to start the api gateway:

```
.\mvnw spring-boot:run
```

### Accessing Customer from API Gateway with Load Balancing

You should now be able to use the following URL to route through the gateway round-robin to the customer service instances:

```
http://localhost:8080/customer-service/api/v1/customers/1
```
