# Microservices Java Eureka-Server

This source code includes 
- One Eureka Server
- Tow Eureka Clients  

## Prerequisites: 
- Java 11
- Spring Boot
- Eureka Discovery Client
- Eureka Server
- Maven
- Gradle

## Configuration Eureka Server
file application.yml

    # Configure this Discovery Server
    eureka:
      instance:
        hostname: localhost
      client: #Not a client
        registerWithEureka: false
        fetchRegistry: false
    
    # HTTP (Tomcat) port
    server:
      port: 1111 

## Configuration Eureka Clientes
Eureka Client2, file application.yml
  
    spring:
      application:
        name: client1-microservice
    # Discovery Server Access
    eureka:
        client:
          serviceUrl:
            defaultZone: http://localhost:1111/eureka/
    server: 
      port: 4200
      
Eureka Client, file application.yml

    spring:
      application:
        name: client2-microservice
    eureka:
        client:
          serviceUrl:
            defaultZone: http://localhost:1111/eureka/
    server: 
      port: 4202
