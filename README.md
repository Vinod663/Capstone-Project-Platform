# Capstone Project - Platform

* **Student Name:** Vinod Niloshana Fernando
* **Student Number:** 241711104
* **Slack Handle:** @Vinod(Vinod Fernando)
* **GCP Project ID:** dark-furnace-506710-f7

---

## Project Description
This repository contains the core infrastructure and routing layer for the Capstone Project microservices architecture. It includes the Spring Cloud API Gateway (which acts as the single entry point for the frontend), the Eureka Service Registry (for dynamic microservice discovery), and the Spring Cloud Config Server (for centralized external configuration). These platform services manage and route traffic to the downstream domain services (Student, Program, and Enrollment).

## Technology Stack
* **Language:** Java 26
* **Framework:** Spring Boot (v4.1.0)
* **Cloud Infrastructure:** Spring Cloud (v2025.1.2)
  * Spring Cloud Gateway
  * Spring Cloud Netflix Eureka
  * Spring Cloud Config
* **Build Tool:** Maven
* **Deployment:** Google Cloud Platform (Compute Engine)

## Setup / Getting Started Instructions

### 1. Prerequisites
* Java 26 (JDK) installed locally.
* Maven installed locally.

### 2. Installation
Clone the repository and build the project using Maven:

```bash
git clone https://github.com/Vinod663/Capstone-Project-Platform.git
cd Capstone-Project-Platform
mvn clean package -DskipTests
```

### 3. Execution Order
Because the microservices depend on these platform components to boot successfully, they must be started in a specific order:

1. **Config Server** — Start this first so other services can fetch their properties.
2. **Eureka Registry** — Start this second so services can register themselves.
3. **API Gateway** — Start this last to begin routing traffic.

### 4. Running Locally
Navigate to each respective platform service's target directory and run the compiled `.jar` file. For example:

```bash
java -jar target/[Service-Name]-1.0.0.jar
```

### 5. Production Deployment (PM2)
On the GCP Virtual Machine, these services are managed and kept alive using PM2. To reload the platform ecosystem without downtime:

```bash
pm2 reload ecosystem.config.js
```