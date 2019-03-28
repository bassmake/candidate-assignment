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

## Technical requirements

* reasonable logging via SLF4J (used implementation is not important) 
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

## Hints for standard three layered approach

### Rest API

![Alt text](https://g.gravizo.com/source/rest_api_mark_1?https%3A%2F%2Fraw.githubusercontent.com%2Fbassmake%2Fcandidate-assignment%2Fmaster%2FREADME.md)
<details> 
<summary></summary>
rest_api_mark_1

@startuml;

title Rest API;

actor Client as u;
participant Controller as c;
participant Service as s;
participant Repository as r;
database DB as db;

u -> c: HTTP request;
c -> s: send data to service method;
s -> r: call repository method;
r -> db: execute query;
db -> r: receive data, map to classes;
r -> s: return business object;
s -> c: return data;
c -> u: HTTP response;

@enduml

rest_api_mark_1
</details>

### Asynchronous processing

![Alt text](https://g.gravizo.com/source/async_mark_1?https%3A%2F%2Fraw.githubusercontent.com%2Fbassmake%2Fcandidate-assignment%2Fmaster%2FREADME.md)

<details>
<summary></summary>
async_mark_1

@startuml;

title Async processing;

actor "external producer" as ep;
participant "message broker" as mb;
participant "message consumer" as mc;
participant Service as s;
participant Repository as r;
database DB as db;

ep ->> mb: produce message;
mc ->> mb: consume message;
mc ->> s: send data to service method;
s -> r: call repository method;
r -> db: execute query;
db -> r: receive data, map to classes;
r -> s: return business object;

@enduml

async_mark_1
</details>
