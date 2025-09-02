# D326 – Advanced Data Management

A backend project demonstrating advanced data modeling and persistence for the **D326** course.  
It focuses on schema design, transactions, query patterns, and clean repository/service layering.

---

## Tech Stack

- **Language:** Java 17
- **Framework:** Spring Boot, Spring Data JPA (Hibernate)
- **Build:** Maven
- **Database:** MySQL (or H2 for local dev)
- **Testing:** JUnit, Spring Boot Test
- **CI:** GitHub Actions (optional)

---

## Features

- Relational schema with entities and relationships (One-to-Many, Many-to-Many as needed)
- Clean Repository → Service → Controller layering
- Transactions and validation on write paths
- Seed/sample data for local runs (`data/samples/`)
- Example queries (derived + JPQL/Criteria)
- Optional DB migrations with Flyway/Liquibase (if present)

---

## Getting Started

### Prerequisites
- Java 17
- Maven 3.9+
- MySQL (or use embedded H2 for quick start)

### Configuration
Create a `.env` (not committed) or set environment variables:

```properties
# application.properties overrides (example)
SPRING_DATASOURCE_URL=jdbc:mysql://localhost:3306/d326?useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
SPRING_DATASOURCE_USERNAME=root
SPRING_DATASOURCE_PASSWORD=<yourpassword>
SPRING_JPA_HIBERNATE_DDL_AUTO=update
