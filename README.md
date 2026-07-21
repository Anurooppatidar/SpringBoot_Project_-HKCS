# SpringBootCrudExample

A RESTful CRUD API built with Spring Boot 3.4.1 and MongoDB, demonstrating a clean, layered architecture (Controller → Service → Repository) with proper exception handling and unit tests.

## Tech Stack

- **Java 17**
- **Spring Boot 3.4.1**
- **Spring Web** (REST API)
- **Spring Data MongoDB**
- **Lombok** (boilerplate reduction)
- **Spring Boot DevTools** (hot reload during development)
- **JUnit 5 & Mockito** (unit testing)
- **Maven** (build tool, via Maven Wrapper)

## Features

- Full CRUD operations (Create, Read, Update, Delete)
- MongoDB document storage and repository-based data access
- Clean, layered project structure for maintainability

## Prerequisites

Before running this project, make sure you have:

- Java 17 or later
- Maven 3.6+ (or use the included `mvnw` / `mvnw.cmd` wrapper, no separate install needed)
- MongoDB instance (local installation or a cloud URI such as MongoDB Atlas)

## Project Structure

```
src
├── main
│   ├── java/com/example/ctpseducation/springbootcrudexample
│   │   ├── controller      # REST endpoints
│   │   ├── service          # Business logic
│   │   ├── repository        # Spring Data MongoDB repositories
│   │   ├── model             # MongoDB document/entity classes
│   │   ├── dto                # Request/response data transfer objects
│   │   ├── exception          # Custom exceptions & global handler
│   │   └── SpringBootCrudExampleApplication.java
│   └── resources
│       └── application.properties
└── test
    └── java/com/example/ctpseducation/springbootcrudexample
        ├── controller
        └── service
```

## Configuration

Update `src/main/resources/application.properties` with your MongoDB connection details:

```properties
spring.data.mongodb.uri=mongodb://localhost:27017/your_database_name
server.port=8080
```

If you're using MongoDB Atlas, replace the URI with your Atlas connection string.

## Getting Started

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd SpringBootCrudExample
   ```

2. **Configure MongoDB** (see [Configuration](#configuration) above)

3. **Build the project**
   ```bash
   ./mvnw clean install
   ```

4. **Run the application**
   ```bash
   ./mvnw spring-boot:run
   ```

   The application will start on `http://localhost:8080` by default.

## API Endpoints

| Method | Endpoint              | Description                  |
|--------|-----------------------|-------------------------------|
| GET    | `/api/items`          | Get all items                |
| GET    | `/api/items/{id}`     | Get a single item by ID       |
| POST   | `/api/items`          | Create a new item             |
| PUT    | `/api/items/{id}`     | Update an existing item       |
| DELETE | `/api/items/{id}`     | Delete an item by ID          |

> **Note:** Replace `items` with the actual resource/entity name used in your project (e.g., `users`, `products`, `employees`). Update this table to reflect your real endpoints, request bodies, and response formats.

## Running Tests

```bash
./mvnw test
```

## Building for Production

```bash
./mvnw clean package
```

The packaged JAR will be available in the `target/` directory and can be run with:

```bash
java -jar target/SpringBootCrudExample-0.0.1-SNAPSHOT.jar
```


