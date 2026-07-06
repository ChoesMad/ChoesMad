## Hi there!👋 I'm Alan
## About Me

Junior Java Developer focused on backend development with Java and Spring Boot.
I've built two REST APIs from scratch: a streaming platform backend with JWT authentication and role-based access,
and a GitHub proxy using Java Virtual Threads and Spring's declarative HTTP clients, with integration tests.
Also comfortable with C# (Unity) and basic web frontend. I enjoy solving real problems and continuously improving the quality of my code.

---

## Known Languages
- Java
- C#
- Python
- HTML & CSS
- JavaScript
- SQL

## Known Tools & Technologies
- Spring Boot, Spring Security, Spring Data JPA / Hibernate
- JWT authentication
- JUnit 5, Mockito, WireMock, MockMvc
- Swagger / OpenAPI
- MySQL
- Git & GitHub
- Gradle
- IntelliJ IDEA, Visual Studio
- Unity

## Some of My Projects

<details>
  <summary>GitHub Proxy REST API (Java 25, Spring Boot 4)</summary>

A REST API that acts as a proxy for the GitHub API, returning a user's non-fork repositories with their branches and last commit SHAs.

### Built With
- Java 25 (Virtual Threads)
- Spring Boot 4
- Spring Web (RestClient, declarative HTTP clients)
- WireMock (integration testing)
- Gradle (Kotlin DSL)

### Features
- Lists a GitHub user's repositories, excluding forks
- Returns branches with the last commit SHA for each repository
- Structured 404 JSON response for unknown users
- Header-based API versioning (X-API-Version)
- Parallel branch fetching using Java Virtual Threads
- Built-in resilience: retries with backoff, concurrency limiting, HTTP timeouts

### Architecture Highlights
- Layered architecture: controller → service → client
- Declarative HTTP client interface (@HttpExchange) registered via @ImportHttpServices
- Retries applied only to transient errors (5xx, timeouts) — 404 is never retried
- Null-safety with JSpecify (@NullMarked)
- Integration tests with WireMock and MockMvc covering fork filtering, empty results, and error responses

This project demonstrates working with the newest Java and Spring Boot features, external API integration, concurrency, and integration testing without mocks.

[Repository](https://github.com/ChoesMad/github-proxy-rest-api)
</details>

<details>
  <summary>StreamCDA Backend API (Java, Spring Boot)</summary>

A backend API for a VOD streaming platform built with Java and Spring Boot.

### Built With
- Java
- Spring Boot
- Spring Security
- JWT Authentication
- Swagger UI
- Hibernate / JPA
- MySQL

### Features
- User registration and login
- JWT-based authentication and authorization
- Role system with USER, PREMIUM, and ADMIN access
- Movie management endpoints
- User management endpoints
- API testing and documentation with Swagger UI

### Architecture Highlights
- RESTful backend architecture
- Secure token-based authentication
- Role-based access control
- Clean separation between controllers, services, and data layers
- API documentation and testing through Swagger UI

This project demonstrates practical backend development skills, secure API design, and working with modern Java web technologies.

[Video](https://youtu.be/yypB-30hrFk)
</details>

<details>
  <summary>3D Banking System Simulation (Unity, C#)</summary>

A structured interactive banking system built in Unity.

### Built With
- C#
- UNITY
- JSON data
  
### Features
- User login & authentication system
- JSON-based user data storage
- Session management using Singleton pattern
- Creditworthiness calculation algorithm
- State-driven dialogue system
- NPC interaction workflow
- Scene transitions & lifecycle handling
- UI panel management
- Player movement & animation control

### Architecture Highlights
- Clear separation between authentication, session storage, business logic, and UI
- Loan system independent from data loading layer
- Manual state machine implementation
- Controlled scene-based application flow

This project demonstrates structured system design, data flow control, and business logic implementation inside an interactive 3D environment. 

[Game video](https://youtu.be/OeWlgDgr2Nk)
</details>

<details>
  <summary>CLI Password Manager (python)</summary>

A secure, zero-knowledge command-line utility for local credential management.

### Built With
- PYTHON
- SQLITE
- CRYPTOGRAPHY (AES-256)
- CLICK & RICH (UI)

### Features
- **AES-256 Symmetric Encryption** for all stored credentials
- **Secure Master Password Hashing** using PBKDF2 with unique salts
- **Local-first SQLite Database** ensuring data privacy and offline access
- **Interactive CLI** with color-coded tables and professional formatting
- **Secure CRUD Operations** (Create, Read, Update, Delete) for accounts

### Architecture Highlights
- **Zero-Knowledge Architecture:** Sensitive data is never stored in plain text; decryption keys exist only in RAM during the active session
- **Authenticated Cryptography:** Implementation of the Fernet standard to prevent unauthorized data tampering
- **Modular Design:** Clear separation between encryption logic, database management, and the CLI layer

This project demonstrates practical backend logic, understanding of cybersecurity principles, and efficient data handling in Python.

[Project video](https://youtu.be/owpl66dOqw0)
</details>

<details>
  <summary> Personal Website (Frontend)</summary>

A responsive personal website built from scratch using pure HTML, CSS, and JavaScript.

### Features
- Responsive layout (desktop & mobile)
- Clean UI structure
- Basic JavaScript interactivity
- Hosted with GitHub Pages

### Built With
- HTML
- CSS
- JavaScript

### Live Demo
[View the website](https://ChoesMad.github.io)

### Purpose
Created to strengthen front-end fundamentals, layout structuring, and UI design principles.

</details>
