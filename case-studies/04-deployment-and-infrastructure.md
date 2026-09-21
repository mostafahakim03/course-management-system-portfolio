# Deployment & Production Infrastructure

## Overview

The MTC Center platform is deployed as a production web application with a separate frontend, backend API, and managed PostgreSQL database.

The production architecture uses Cloudflare Pages for the frontend, a VPS for the backend, Docker for containerization, Nginx as a reverse proxy, and Neon for managed PostgreSQL.

---

## Production Architecture

```text id="k7p2x"
                         Internet
                            │
                            ▼
                  ┌──────────────────┐
                  │    Cloudflare     │
                  │      Pages       │
                  └────────┬─────────┘
                           │
                           │ HTTPS
                           ▼
                  ┌──────────────────┐
                  │      React       │
                  │     Frontend     │
                  └────────┬─────────┘
                           │
                           │ HTTPS / REST API
                           ▼
                https://api.mtccenters.com
                           │
                           ▼
                  ┌──────────────────┐
                  │      Nginx       │
                  │  Reverse Proxy   │
                  │  HTTPS / SSL     │
                  └────────┬─────────┘
                           │
                           ▼
                  ┌──────────────────┐
                  │      Docker      │
                  │                  │
                  │   Spring Boot    │
                  │    Backend API   │
                  └────────┬─────────┘
                           │
                           │ PostgreSQL
                           ▼
                  ┌──────────────────┐
                  │       Neon       │
                  │    PostgreSQL    │
                  └──────────────────┘
```

---

## Frontend Deployment

The React frontend is deployed using **Cloudflare Pages**.

The production website is available through the custom domain:

**https://mtccenters.com**

The frontend is responsible for the user interface and communicates with the backend through REST API requests.

Cloudflare Pages provides the production hosting and delivery layer for the React application.

---

## Backend Deployment

The backend is built with **Spring Boot** and deployed on a VPS.

The Spring Boot application runs inside a **Docker container**, providing a consistent and isolated runtime environment.

The production API is available through:

**https://api.mtccenters.com**

The backend is responsible for:

* Authentication and authorization.
* Business logic.
* Course and batch management.
* Student enrollment.
* Lecture and resource management.
* Admin operations.
* Database communication.
* API security.

---

## Nginx Reverse Proxy

**Nginx** is used on the VPS as a reverse proxy in front of the Spring Boot application.

Instead of exposing the Spring Boot container directly to the internet, incoming requests first reach Nginx.

Nginx then forwards the requests to the appropriate backend application running inside Docker.

```text id="w6h4n"
Client
  │
  │ HTTPS
  ▼
Nginx
  │
  │ Reverse Proxy
  ▼
Spring Boot
  │
  ▼
Docker Container
```

This provides a clean separation between the public-facing web layer and the backend application.

---

## HTTPS & SSL Configuration

The production API is exposed through an HTTPS-enabled domain.

Nginx is configured as part of the HTTPS production setup, allowing secure communication between clients and the backend API.

HTTPS is used for:

* The public website.
* Backend API requests.
* Communication between the React frontend and Spring Boot backend.

This protects data while it is transmitted between the user's browser and the production services.

The exact certificate-management mechanism is kept as an infrastructure detail rather than exposing sensitive production configuration in the public portfolio.

---

## Frontend → Backend Communication

The React application communicates with the Spring Boot backend through REST APIs.

```text id="r1v8c"
Browser
   │
   │ HTTPS
   ▼
mtccenters.com
   │
   │ REST API
   ▼
api.mtccenters.com
   │
   ▼
Nginx
   │
   ▼
Spring Boot
   │
   ▼
Neon PostgreSQL
```

The separation between the frontend and backend allows each service to be deployed and maintained independently.

---

## Database — Neon PostgreSQL

The production database uses **PostgreSQL hosted on Neon**.

The Spring Boot backend connects to the managed PostgreSQL database through the configured production database connection.

Using Neon keeps the database infrastructure separate from the application VPS and avoids running the PostgreSQL database directly inside the backend server.

---

## Docker Deployment

The Spring Boot backend is containerized using Docker.

The deployment architecture can be summarized as:

```text id="u3n9p"
Spring Boot Application
          │
          ▼
      Docker Image
          │
          ▼
          VPS
          │
          ▼
   Docker Container
          │
          ▼
        Nginx
          │
          ▼
     Public HTTPS API
```

Docker provides a consistent runtime environment and simplifies deployment and application management on the VPS.

---

## Production Configuration

The production environment uses separate configuration for deployment-specific settings, including:

* Database connection.
* API configuration.
* CORS configuration.
* Security configuration.
* HTTPS-related configuration.
* Application environment settings.
* Production secrets and credentials.

Sensitive values are not stored in the public portfolio repository.

The public repository does not contain:

* Database passwords.
* JWT secrets.
* API keys.
* Production credentials.
* Private infrastructure configuration.

---

## Deployment Architecture Benefits

This deployment structure provides:

* Separate frontend and backend services.
* Managed PostgreSQL through Neon.
* Docker-based backend deployment.
* Nginx reverse proxy.
* HTTPS-enabled production API.
* Independent frontend deployment through Cloudflare Pages.
* Clear REST API separation.
* Secure handling of production configuration.
* A scalable foundation for future platform features.

---

## Production URLs

* **Website:** https://mtccenters.com
* **Backend API:** https://api.mtccenters.com
* **Frontend Hosting:** Cloudflare Pages
* **Backend Hosting:** VPS + Docker + Nginx
* **Database:** Neon PostgreSQL
