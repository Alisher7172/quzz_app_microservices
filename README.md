# Quiz App Microservices

A small Spring Boot microservices project for managing quiz questions and quiz generation.

## Overview

This project contains four services:

- `service-registry` — Eureka service discovery server
- `api-gateway` — Spring Cloud Gateway entry point
- `question-service` — stores and serves quiz questions
- `quiz-service` — creates quiz logic and communicates with the question service

The app uses Java 17, Spring Boot 3, Spring Cloud, PostgreSQL, and Maven.

## Prerequisites

- Java 17+
- Maven
- PostgreSQL
- Databases created for the app: `questiondb` and `quizdb`

## Run the project

1. Start the registry:
   ```bash
   cd service-registry
   mvn spring-boot:run
   ```

2. Start the question service:
   ```bash
   cd question-service
   mvn spring-boot:run
   ```

3. Start the quiz service:
   ```bash
   cd quiz-service
   mvn spring-boot:run
   ```

4. Start the API gateway:
   ```bash
   cd api-gateway
   mvn spring-boot:run
   ```

## Configuration

The services expect PostgreSQL credentials in their `application.properties` files. You may also import the sample data from `question-table-data.sql` into `questiondb`.

## Notes

- Service registry: `http://localhost:8761`
- API gateway: `http://localhost:8765`

This project is a basic example of a Java microservice architecture with discovery, routing, and separate data services.
