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

![rest](https://www.plantuml.com/plantuml/svg/LP1BJWCn38RtFeKF01UO1Iej2zXLRI-GE9O8oYI3xLJqzesPQgGku-z_sDcf1R4-5m3BLXXFh8Rlno-0GDO43oLpDGoA7POXpPINC0Q7LarQAIpEw8cTMQwPs84-WHClJVE8lJaJIC523ChuiVT1YW0TNz-G9loyN8ue_Dl7Fa0-r0cLQq8teRNnM5jcjk-MG5qZ4r8ePHYteWSMnobEo7zCtHX7ijmWnOTDc3XV-J_z1UUmU0MLeCgwcjL5rgLYx9ehgsABFqosLjE6FM9TkMztwDAgCi1kN31--mu0)

### Asynchronous processing

![async](https://www.plantuml.com/plantuml/svg/NP5DJaCn38JtFeNLDLoWYweWJW0dI1oh15v-i9sglNqT-afLbiatdXdPUxKWDie2ODaMnXSzLy8kZLWrrmD086k26puPImtBP6aGomQ38dVu6JmODyNruS0OfNsli4Jexfufzr3jBg5MTPIRY1v47op7J3o9Fe1txaspLpbF9f22XHYKyUrrVgG8m1sVTpkFtTvAuXe9XVxGcluVwHQLQyBfYzRySIrIs3vR0dKHYa-7PK6vTrcnJ9pSdKzCmnXzAtA65DSnOU9yv5_t9ooXpmXQWYhhTLYdo8PKZCCNx-MmnIyc0zXxBp_H1G00)
