# ⚙️ Spring Cloud Config Server

Centralized Configuration Server for the **Hotel Booking Microservices Platform** built using **Spring Cloud Config Server**. It externalizes configuration from all microservices and provides environment-specific properties from a centralized Git repository.

---

# 🚀 Features

- Centralized Configuration Management
- Externalized Application Properties
- Environment-Specific Profiles (dev, test, prod)
- Git-Based Configuration Repository
- Dynamic Configuration Loading
- Integration with Spring Boot Microservices
- Easy Configuration Updates
- Scalable Configuration Architecture

---

# 🏗 Responsibilities

The Config Server is responsible for:

- Serving configuration files to all microservices
- Managing environment-specific properties
- Centralizing application configuration
- Eliminating duplicate configuration across services
- Supporting profile-based configurations

---

# 📦 Technology Stack

| Technology | Usage |
|------------|-------|
| Java | Programming Language |
| Spring Boot | Application Framework |
| Spring Cloud Config Server | Centralized Configuration |
| Git | Configuration Repository |
| Maven | Dependency Management |

---

# 📁 Project Structure

```
Config-Server
│
├── src
│   ├── main
│   │   ├── java
│   │   └── resources
│   │       └── application.yml
│   └── test
│
├── pom.xml
└── README.md
```

---

# 🔄 How It Works

```
                  Git Repository
                         │
                         ▼
              Spring Cloud Config Server
                         │
      ┌──────────────────┼──────────────────┐
      ▼                  ▼                  ▼
 User Service      Hotel Service      Rating Service
                         │
                         ▼
                  Booking Service
                         │
                         ▼
                    API Gateway
```

---

# 📂 Configuration Repository

The Config Server fetches configuration files from a Git repository.

Example:

```
application.yml

user-service.yml

hotel-service.yml

rating-service.yml

booking-service.yml

api-gateway.yml
```

Environment-specific configurations:

```
user-service-dev.yml

user-service-test.yml

user-service-prod.yml
```

---

# ⚙ Configuration Flow

1. Microservice starts.
2. Microservice requests configuration from Config Server.
3. Config Server retrieves configuration from the Git repository.
4. Configuration is returned to the requesting service.
5. Microservice loads the received configuration during startup.

---

# 🔗 Configuration Endpoints

| Endpoint | Description |
|----------|-------------|
| `/application/default` | Default application configuration |
| `/user-service/default` | User Service configuration |
| `/hotel-service/default` | Hotel Service configuration |
| `/rating-service/default` | Rating Service configuration |
| `/booking-service/default` | Booking Service configuration |
| `/api-gateway/default` | API Gateway configuration |

---

# ▶️ Running the Project

## Clone Repository

```bash
git clone https://github.com/your-username/config-server.git
```

## Build

```bash
mvn clean install
```

## Run

```bash
mvn spring-boot:run
```

or

```bash
java -jar target/config-server.jar
```

---

# 🔧 Client Configuration

Each microservice imports configuration from the Config Server.

Example (`application.yml`):

```yaml
spring:
  application:
    name: user-service

  config:
    import: optional:configserver:http://localhost:8888
```

---

# 🔥 Key Highlights

- Centralized Configuration Management
- Git-Based Configuration Repository
- Environment-Specific Profiles
- Spring Cloud Config Server
- Easy Configuration Maintenance
- Scalable for Multiple Microservices
- Reduces Configuration Duplication

---

# 👨‍💻 Author

**Abhishek Kanade**

Java Backend Developer | Spring Boot | Spring Cloud | Microservices | Distributed Systems
