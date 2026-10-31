# College Management System

A robust, multi-module backend system built using **Java** and **Spring Boot**, implementing a microservices architecture to manage student services, centralized configuration, service discovery, and authentication.

---

## 🏗️ Architecture Overview

This project is built using a microservices pattern, allowing individual services to scale independently while sharing configuration and discovery tools.

```
                  +-------------------------+
                  |  Eureka Discovery Server|
                  +------------+------------+
                               |
       +-----------------------+-----------------------+
       |                       |                       |
+------v-------+        +------v-------+        +------v-------+
| Auth Service |        | Student Svc  |        | Downstream Svc|
+--------------+        +--------------+        +--------------+
       ^                       ^                       ^
       +-----------------------+-----------------------+
                               |
                    +----------+----------+
                    |  Config Server      |
                    +---------------------+

```

* **Eureka Discovery Server**: Registers and dynamically locates available microservice instances.
* **Config Server**: Centralizes configuration properties for all microservices across different environments.
* **Auth Service**: Handles user authentication, security, and session/token management.
* **Student Service**: Manages core domain logic for student data, enrollments, and academic profiles.
* **Downstream Service**: Handles supplementary integrations and background operations downstream.

---

## 🛠️ Tech Stack & Dependencies

* **Language**: Java 100%
* **Framework**: Spring Boot, Spring Cloud (Eureka, Config Server)
* **Security**: Spring Security / JWT (Auth Service)
* **Build Tool**: Maven / Gradle

---

## 📁 Repository Structure

```
microservices-repo/
├── student-service/          # Student management domain logic
├── authservice.zip           # Authentication and authorization service
├── Config Server.zip         # Centralized configuration server
├── Eureka Discovery Server.zip# Service registry and discovery
├── Downstream Service.zip    # Secondary processing service
├── Demo111Application.java   # Core application entry point
└── README.md                 # Project documentation

```

---

## 🚀 Getting Started

### Prerequisites

* **JDK**: Version 17 or higher
* **Maven**: Version 3.8+
* **IDE**: IntelliJ IDEA / Eclipse / VS Code

### Run Order

To spin up the system correctly, start the infrastructure microservices before the application services:

1. **Start Eureka Discovery Server**
Runs on port `8761` (default). Tracks registered instances.
2. **Start Config Server**
Runs on port `8888` (default). Provides configurations to client services.
3. **Start Auth Service**
Provides authentication capabilities.
4. **Start Student Service & Downstream Services**
Connects to Eureka and pulls config settings on launch.

---

## ⚙️ Configuration & Execution

Clone the repository and run any individual service using Maven:

```bash
git clone https://github.com/RachitMohal543/microservices-repo.git
cd microservices-repo

# Run a specific Spring Boot service module
cd student-service
mvn spring-boot:run

```

---

## 🤝 Contributing

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.
