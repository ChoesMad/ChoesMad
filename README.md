## Hi there!👋 I'm Alan
## About Me

Junior Unreal Engine Developer (C++) passionate about building real-time, interactive
3D systems — from gameplay logic to the data feeding it. I recently shipped a
full-stack property visualization app: a Spring Boot REST API driving a live,
interactive Unreal Engine 5 scene, with real-time filtering, reservations, and
purchases reflected instantly in the 3D world. 
I also enjoy working on the backend side of things — building REST APIs, thinking
through state machines and system architecture — which means I tend to think about
gameplay features not just as isolated code, but as part of a whole system talking
to a server, a database, or another layer underneath. Comfortable in both Unreal
(C++, Blueprints/UMG) and Unity (C#), and I like picking apart *why* something is
built a certain way, not just getting it to run.

---

## Known Languages
- C++
- Java
- C#
- Python
- HTML & CSS
- JavaScript
- SQL

## Known Tools & Technologies
- Unreal Engine 5
- Unity
- Spring Boot, Spring Security, Spring Data JPA / Hibernate
- JWT authentication
- JUnit 5, Mockito, WireMock, MockMvc
- Git & GitHub
- Gradle
- IntelliJ IDEA, Visual Studio

## Some of My Projects

<details>
  <summary>Real-Time Interactive Estate Hub (UE5, C++, Spring Boot, PostgreSQL)</summary>
    
An interactive 3D residential estate visualization powered by real-time REST data. Allows users to filter apartments, click buildings in a 3D environment, reserve, and purchase units — dynamically recoloring building window materials live without page or scene reloads.
### Built With
- Unreal Engine 5.8 (C++, Enhanced Input, UMG)
- Java 25 & Spring Boot 4.1.1
- Spring Data JPA & PostgreSQL
- Gradle (Kotlin DSL)
- JUnit 5 & Spring Boot Test (MockMvc, @DataJpaTest)

### Features
- Real-time 3D window material recoloring across 35 physical building actors (506 total apartments) based on status (Available, Reserved, Sold)
- Interactive client-side filtering by price, room count, and garage availability that dynamically updates 3D visual feedback
- Interactive 3D building selection featuring UMG UI panels for reserving and purchasing units
- Backend-enforced state machine ensuring strict status lifecycle transitions (AVAILABLE → RESERVED → SOLD) with explicit error handling (409 Conflict)
- Comprehensive REST API providing health checks, apartment listing/filtering, reservation, and purchasing endpoints

### Architecture Highlights
- Event-Driven C++ Subsystem (UEstateApiSubsystem): Serves as the single source of truth in Unreal Engine, utilizing dynamic delegates with zero Tick() polling overhead
- Dynamic Material Recoloring: Overcomes merged mesh geometry transform constraints by modifying material instance slots (UMaterialInstanceDynamic) directly rather than actor transforms
- In-Memory Client Filtering: Caches backend data locally to make interactive UI sliders instant while eliminating HTTP request flooding
- Clean Backend Layering: Classic Controller → Service → Repository structure with strict DTO/Entity isolation and explicit exception mapping
- Comprehensive Backend Testing: Multi-layered test coverage across JPA repositories, services, and REST controllers validating all state machine transitions

This project demonstrates C++ REST integration in Unreal Engine 5, event-driven 3D visual reactivity, backend state machine enforcement, and clean client-server architecture.

[Game video](https://youtu.be/CzkQj9QpNNQ)
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
  <summary>Game Backlog Tracker</summary>
A REST API for tracking a personal video game backlog, enabling users to search games via the RAWG database, import them into a local library, and manage play statuses and ratings.

### Built With
- Java 25 (Virtual Threads, Records, Text Blocks)
- Spring Boot 4.1 & Spring Framework 7
- Spring Data JPA, Hibernate 7, PostgreSQL 17
- Flyway (Database Migrations)
- Declarative @HttpExchange client over RestClient
- Native Resilience (@Retryable, @ConcurrencyLimit)
- JSpecify (@NullMarked)
- Testcontainers & WireMock (Integration Testing)
- Gradle 9 (Kotlin DSL)

### Features
- Search games on RAWG API via a lightweight proxy
- Idempotent game importing with parallel details fetching using Java Virtual Threads
- Complete backlog lifecycle tracking (Planned, Playing, Completed, Dropped with optional 1–10 ratings)
- Header-based API versioning (X-API-Version)
- Standardized error responses (ApiError) for validation, proxy timeouts, and upstream failures
- Paginated and sortable backlog listings

### Architecture Highlights
- Deliberately flat, three-layer architecture (Controller → Service → Repository / Gateway) with entity/DTO isolation using Java Records
- Zero-dependency resilience using native Spring Framework 7 annotations (@Retryable for transient 5xx/timeouts, @ConcurrencyLimit for Virtual Threads protection)
- Database schema fully owned by Flyway migrations (ddl-auto=validate)
- Efficient JPA fetch strategies using lazy relations paired with @EntityGraph to prevent N+1 queries
- Off-thread RAWG imports keeping database connection hold times to a minimum
- Fast, reproducible integration testing using real PostgreSQL containers and WireMock HTTP stubs

This project demonstrates modern Spring Boot 4 and Java 25 capabilities, lightweight resilience patterns, clean API design, and integration testing without external dependencies.

[Repository](https://github.com/ChoesMad/game-backlog-tracker)
</details>

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
