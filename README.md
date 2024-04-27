A Spring Boot CRUD Application Example

Introduction to Spring Boot
Spring Boot Overview
Spring Boot stands out as one of the premier projects within the Spring ecosystem. It simplifies the configuration and deployment of enterprise applications, offering a streamlined experience. With Spring Boot, developers can swiftly create robust, production-ready Spring-based applications with minimal setup. The framework adopts an "opinionated" stance, providing default configurations that alleviate much of the developer's burden.

To bootstrap a Spring Boot application, one merely needs to define a Java class annotated with @SpringBootApplication. This annotation encapsulates other annotations such as @Configuration, @EnableAutoConfiguration, and @ComponentScan, simplifying setup and initialization.

Understanding CRUD Applications
In the realm of microservice frameworks, CRUD (Create, Read, Update, Delete) applications serve as foundational components. They encapsulate essential functionalities that power APIs, making them akin to a "Hello World" in this domain. These applications handle basic data operations, serving as the building blocks for more complex systems.

Project Organization
When structuring a Spring Boot project, there's flexibility in defining package hierarchies. However, for clarity and adherence to best practices, this sample project adheres loosely to the MVC (Model-View-Controller) pattern. Each package serves a distinct purpose, facilitating organization and maintenance.

The project's base folders include:

application: Contains the main class booting up the application.
builder: Houses utility classes for entity-DTO conversion.
config: Holds Spring configuration classes defining beans.
controller: Contains classes responsible for processing REST API requests.
exception: Houses custom exceptions for handling data consistency and business rule violations.
domain: Contains POJO classes annotated with @Entity, representing database entities.
dto: Houses DTO classes facilitating data transfer across architectural boundaries.
repository: Contains classes annotated with @Repository for data access operations.
service: Contains classes annotated with @Service where business logic resides.
Prerequisites
Ensure the following prerequisites are met before running the application:

Maven 3+
Java 8+
Dependencies
The project relies on several libraries and dependencies to function effectively:

Spring Web
Spring Data JPA
JUnit 5
Mockito
Hamcrest
H2 Database
Lombok
ModelMapper
JavaFaker
Sample Project Overview
This sample project implements an API for managing applications produced by a project management software company. Each application release is represented by its name, version, and developer. The project utilizes an H2 in-memory database, though configuration for a real database like MySQL is straightforward.

Booting Up the Application
To run the application, follow these steps:

Clone the repository:
bash
git clone https://github.com/davidarchanjo/spring-boot-crud-rest
Navigate to the project folder:
bash
cd spring-boot-crud-rest
Run the application:
bash
mvn spring-boot:run
Testing the API
The API endpoints can be tested using tools like Postman or cURL. Here's how to interact with the API:

Create New App
URL: http://127.0.0.1:8080/api/v1/apps
Method: POST
Body:
json
{
  "appName": "netflix",
  "appVersion": "0.0.0",
  "devName": "David Archanjo"
}
Get App by ID
URL: http://127.0.0.1:8080/api/v1/apps/{appId}
Method: GET
Update App
URL: http://127.0.0.1:8080/api/v1/apps/{appId}
Method: PUT
Body:
json
{
  "appName": "netflix",
  "appVersion": "1.0.0",
  "devName": "David Archanjo"
}
Delete App
URL: http://127.0.0.1:8080/api/v1/apps/{appId}
Method: DELETE
Unit Testing
Unit tests are crucial for ensuring the robustness of any application. This project includes unit tests leveraging JUnit 5, Mockito, and Hamcrest. These tests validate the functionality of controllers and integration points within the application.

To execute the tests, run:

bash
mvn test
Conclusion
This project aims to showcase the fundamental aspects of a Spring Boot CRUD application. While it doesn't encompass the entirety of Spring Boot's capabilities, it provides a solid foundation for understanding and building upon. Feel free to explore and expand upon this sample project to suit your requirements!
