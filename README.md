# candidate-assignment
Assignment for potential candidates

# Business 

## Business background
Application where you can track/add/reduce points for customers. Points can be earned by processing
monetary transactions.

## Business requirements

* CRUD for customer(name, points, points history)
* Async transaction(id, amount) processing from message broker with adding points based on amount

# Technical 

## Technical stack (choose one)

* [Lagom](https://www.lagomframework.com/)
  * Language: Scala or Java 
  * Build tool: Sbt or Maven
  * Message broker: Kafka (built in support)
  * Persistence: Cassandra or JDBC 
* [Spring boot](https://spring.io/projects/spring-boot)
  * Language: Kotlin or Java 
  * Build tool: Gradle or Maven
  * Message broker: Kafka or ActiveMQ
  * Persistence: Jooq or JPA 
* [Micronaut](https://micronaut.io/)
  * Language: Kotlin or Java 
  * Build tool: Gradle or Maven
  * Message broker: Kafka or ActiveMQ
  * Persistence: Jooq or JPA

## Architecture

### Rest API

<img src='https://g.gravizo.com/svg?
@startuml;

actor User;
participant "First Class" as A;
participant "Second Class" as B;
participant "Last Class" as C;

User -> A: DoWork;
activate A;

A -> B: Create Request;
activate B;

B -> C: DoWork;
activate C;

C --> B: WorkDone;
destroy C;

B --> A: Request Created;
deactivate B;

A --> User: Done;
deactivate A;

@enduml
'>

### Asynchronous processing

## Technical requirements

* Unit tests
* Integration tests - this means that whole application is running including in-memory DB

### Bonus points

* Domain Driven Design applied
* Multi-module approach with [clean architecture](https://medium.freecodecamp.org/a-quick-introduction-to-clean-architecture-990c014448d2)
* Generated API documentation
* Automated DB migrations ([Liquibase](https://www.liquibase.org/) or [Flyway](https://flywaydb.org/))
* Security layer with basic auth
* Security layer with JWT
* Building runnable fat-jar