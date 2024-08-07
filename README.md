# Spring Boot Kafka Microservices [![Build Status](https://github.com/prafullsranjan/simple-spring-boot-security-jwt/actions/workflows/maven.yml/badge.svg)](https://github.com/prafullsranjan/simple-spring-boot-security-jwt/actions/workflows/maven.yml) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white) ![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white) ![Apache Kafka](https://img.shields.io/badge/Apache%20Kafka-000?style=for-the-badge&logo=apachekafka) ![Apache Maven](https://img.shields.io/badge/Apache%20Maven-C71A36?style=for-the-badge&logo=Apache%20Maven&logoColor=white) 

A simple Spring-Boot microservice application to demo Apache Kafka producer-consumer concept.

In this project we've 4 submodules in which 3 are basically microservices and `base-libs` is a standalone project for DTO.

Out of the three microservices, ```producer-order-service``` microservice is the producer using which we can create an event and the other two - ```consumer-inventory-service``` & ```consumer-notification-service``` are the microservices which will consume the order event.

## Installation Instructions
You can import the project as a maven application to your favorite IDE. I made my tests by using IntelliJ.

## To run the application
1. Install Apache Kafka and follow the mentioned steps [here](https://kafka.apache.org/quickstart).
2. Run Zookeeper & Apache Kafka server.
3. Start the ```producer-order-service``` as a Spring-Boot application.
4. Start the ```consumer-notification-service``` & ```consumer-inventory-service``` also as Sprint-Boot application.

## Test the service
1. Make a post request to the endpoint - `http://localhost:8080/api/order` with the request as: 
   `{
   "name": "my order",
   "quantity": 10,
   "price": 1000
   }`
2. After receiving the `200` response code with success message as `Order placed successfully...`, check the logs of all three microservices and you'll get the logs of producer & consumers in the producer & consumer services respectively with the order details.
