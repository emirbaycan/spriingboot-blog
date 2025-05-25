# Spring Boot Blog

A modern, production-ready blogging platform built with Spring Boot, Java, and Docker. Features user registration/login, post creation & editing, image upload, RSS feed support, database migrations, and a full MVC architecture. Easily run locally or deploy with Docker Compose for automated database provisioning.

---

## Features

* User registration & login
* Create, edit, delete, and view blog posts
* Image upload support for posts
* RSS feed endpoint for syndication
* Thymeleaf-powered HTML templates
* Database migrations (SQL)
* Runs locally or fully containerized with Docker
* Clean MVC structure: Controllers, Services, Repositories, Models

---

## Tech Stack

* **Backend:** Java 17+, Spring Boot
* **Frontend:** Thymeleaf, HTML5/CSS3
* **Database:** MySQL (default, via Docker), or custom JDBC
* **ORM:** Spring Data JPA (Hibernate)
* **Build:** Maven
* **DevOps:** Docker, Docker Compose, Flyway (migrations)

---

## Quick Start (Local Development)

### 1. Prerequisites

* Java 17+
* Maven
* MySQL (if not using Docker)

### 2. Clone the Repository

```bash
git clone https://github.com/emirbaycan/springboot-blog.git
cd springboot-blog
```

### 3. Configure Database

* Edit `src/main/resources/application.properties` for DB connection settings (if not using Docker Compose)

### 4. Build & Run

```bash
# On Windows
del /s /q target
mvnw clean install
mvnw spring-boot:run

# On Mac/Linux
rm -rf target
./mvnw clean install
./mvnw spring-boot:run
```

* App should be available at: [http://localhost:8080](http://localhost:8080)

---

## Quick Start (Dockerized)

### 1. Prerequisites

* Docker & Docker Compose

### 2. Run All Services

```bash
docker-compose up --build
```

* This will automatically build the Java app and start the database service.
* App will be available at: [http://localhost:8080](http://localhost:8080)

---

## Database Migrations

* All DB migration scripts are located in `src/main/resources/db/migration/` and run automatically by Flyway.
* To add a new migration, add a new `V*_*.sql` file following Flyway naming conventions.

---

## Folder Structure

```
src/main/java/com/emirbaycan/portfolio
  ├── config/
  ├── controllers/
  ├── models/
  ├── repositories/
  ├── services/
  └── PortfolioApplication.java
src/main/resources/
  ├── css/
  ├── db/migration/
  │   ├── V1_initial_migration.sql
  │   └── V2_add_imageFilePathToPost.sql
  ├── templates/
  │   ├── 404.html
  │   ├── error.html
  │   ├── home.html
  │   ├── login.html
  │   ├── post_edit.html
  │   ├── post_new.html
  │   ├── post.html
  │   └── register.html
  └── application.properties
```

---

## Configuration

* All environment-specific settings (DB connection, server port, etc.) are in `application.properties`.
* For Docker, these are typically set via environment variables in `docker-compose.yml`.

---

## License

MIT © Emir Baycan

---

## Author

Developed and maintained by [Emir Baycan](https://emirbaycan.com.tr/)
