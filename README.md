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

![rest-api](https://g.gravizo.com/source/svg/rest?http%3A%2F%2Fwww.gravizo.com)
![rest-api](http://www.gravizo.com/img/1x1.png#
rest        
@startuml
object Object01
object Object02
object Object03
object Object04
object Object05
object Object06
object Object07
object Object08

Object01 <|-- Object02
Object03 *-- Object04
Object05 o-- "4" Object06
Object07 .. Object08 : some labels
@enduml
rest        
        

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