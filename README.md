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

![Alt text](https://g.gravizo.com/source/custom_mark10?https%3A%2F%2Fraw.githubusercontent.com%2Fbassmake%2Fcandidate-assignment%2Fmaster%2FREADME.md)
<details> 
<summary></summary>
custom_mark10
  digraph G {
    size ="4,4";
    main [shape=box];
    main -> parse [weight=8];
    parse -> execute;
    main -> init [style=dotted];
    main -> cleanup;
    execute -> { make_string; printf};
    init -> make_string;
    edge [color=red];
    main -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
custom_mark10
</details>

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