# Service-Registry

A Netflix Eureka service registry used by the API Gateway and all Cloud Health domain microservices.

## About

This project is part of the Cloud Health Project for ITS 2130 Enterprise Cloud Architecture. It provides service registration, discovery, health visibility, and logical service-name resolution without hard-coded instance addresses.

## Tech Stack

| Technology | Details |
|---|---|
| Java | 25 |
| Spring Boot | 4.1.0 |
| Spring Cloud | 2025.1.2 |
| Netflix Eureka Server | Service registry |
| Spring Cloud Config Client | External configuration |
| Spring Boot Actuator | Health and readiness endpoints |
| Maven Wrapper | Reproducible builds |

## Service Details

| Property | Value |
|---|---|
| Port | `8761` |
| Eureka application name | `service-registry` |
| Artifact ID | `discovery-server` |
| Group ID | `com.cloudhealth` |
| Config Server | `http://localhost:8888` |
| Eureka dashboard | `http://localhost:8761` |
| Repository | `Cloud-Health-Project-Platform-Discovery-Server` |

## Getting Started

> **Prerequisite:** Config-Server must be running on port `8888`.

Startup order:

1. Config Server (`8888`)
2. **Service-Registry** (`8761`)
3. API Gateway and domain services

```bash
./mvnw spring-boot:run
```

Open `http://localhost:8761` to inspect registered services.

For peer-aware Google Cloud deployment, provide a comma-separated `EUREKA_DEFAULT_ZONE` containing the registry peers and enable `EUREKA_REGISTER_WITH_EUREKA` and `EUREKA_FETCH_REGISTRY`. The service then appears as `SERVICE-REGISTRY` on the Eureka dashboard.

## Testing

```bash
./mvnw test
```

## Project Details

| Property | Value |
|---|---|
| Student | Hiruna Dissanayake |
| Student number | `241711024` |
| GCP project | `cloud-health-506015-hiruna` |
