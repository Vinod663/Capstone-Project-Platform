# Capstone Project - Domain Services

* **Student Name:** Vinod Niloshana Fernando
* **Student Number:** 241711104
* **Slack Handle:** @Vinod(Vinod Fernando)
* **GCP Project ID:** dark-furnace-506710-f7

---

## Project Description
This repository contains the backend domain microservices for the Capstone Project, encompassing the `student-service`, `program-service`, and `enrollment-service`. These services handle core business logic, database transactions (PostgreSQL and MongoDB), and file storage integrations (Google Cloud Storage). They are designed to register with the Eureka Service Registry and fetch configurations from the centralized Config Server.

## Technology Stack
* **Language:** Java 26
* **Framework:** Spring Boot (v4.1.0)
* **Databases:** PostgreSQL (Relational) & MongoDB (NoSQL)
* **Cloud Storage:** Google Cloud Storage (GCP Buckets)
* **Database Connectivity:** Google Cloud SQL Auth Proxy
* **Build Tool:** Maven
* **Process Manager:** PM2 (Node.js)
* **Deployment:** Google Cloud Platform (Compute Engine)

## Setup / Getting Started Instructions

**1. Prerequisites**
* Java 26 (JDK) installed locally.
* Maven installed locally.
* A valid GCP Service Account JSON key (if running locally) with `Cloud SQL Client` and `Storage Object Admin` permissions.

**2. Installation**
Because this repository relies on individual microservice folders linked as Git submodules, clone the repository using the recurse flag:
```bash
git clone --recurse-submodules https://github.com/Vinod663/Capstone-Project-Services.git
cd Capstone-Project-Services
```