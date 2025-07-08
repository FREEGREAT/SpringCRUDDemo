# SpringCRUDDemo

A simple Spring Boot CRUD application for managing users, using PostgreSQL, JPA, and Flyway for database migrations.

## 🚀 Tech Stack

- Java 24
- Spring Boot 3.5.3
- Spring Data JPA
- PostgreSQL
- Flyway
- Maven

## 📦 Getting Started

### Prerequisites

- Java 24
- Maven 3.8+
- PostgreSQL installed and running

### Database Setup

Create a PostgreSQL database:

```sql
CREATE DATABASE spring_crud_demo;
```

### Configuration

Edit `src/main/resources/application.properties` to set your database credentials:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/spring_crud_demo
spring.datasource.username=your_username
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=none
spring.jpa.show-sql=true

spring.flyway.enabled=true
spring.flyway.locations=classpath:db/migration
```

### Running the Application

Clone the repo, then run:

```bash
git clone https://github.com/FREEGREAT/SpringCRUDDemo.git
cd SpringCRUDDemo
mvn spring-boot:run
```

Flyway will automatically run database migrations on startup.

## 📡 REST API

Base path: `/api/users`

| Method | Endpoint          | Description                |
|--------|-------------------|----------------------------|
| GET    | `/api/users`      | Get all users              |
| POST   | `/api/users`      | Create a new user          |
| PUT    | `/api/users/{id}` | Update user email and/or name (via query params) |
| DELETE | `/api/users/{id}` | Delete user by ID          |

### Example cURL Requests

- Get all users:

```bash
curl -X GET http://localhost:8080/api/users
```

- Create user:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"name":"John Doe","email":"john@example.com"}' http://localhost:8080/api/users
```

- Update user:

```bash
curl -X PUT "http://localhost:8080/api/users/1?name=Jane%20Doe&email=jane@example.com"
```

- Delete user:

```bash
curl -X DELETE http://localhost:8080/api/users/1
```

## 📂 Project Structure

```
SpringCRUDDemo/
├── src/
│   ├── main/
│   │   ├── java/com/example/demo/     # Application code
│   │   └── resources/
│   │       ├── application.properties
│   │       └── db/migration/          # Flyway migrations
├── pom.xml                            # Maven configuration
```

## 📄 License

This project is open for educational and demonstration purposes.

## 👤 Author

GitHub: [FREEGREAT](https://github.com/FREEGREAT)