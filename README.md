# Jetly Backend

Jetly is a Bitly-inspired URL shortener.
This repository contains the **backend service** built with **Java Spring Boot**, providing a secure API with JWT authentication and integration with a cloud-hosted PostgreSQL database on **Neon DB**.
The backend is hosted on **Back4App**.

---

## Features

* 🔐 **JWT Authentication** – secure user login and request validation
* 🔗 **URL Shortening** – generate short URLs that redirect to long URLs
* 📊 **Analytics** – track total clicks for shortened links
* ☁️ **Cloud Database** – PostgreSQL hosted on Neon DB
* 🌐 **Production Hosting** – deployed on Back4App

---

## Tech Stack

* **Java 25**
* **Spring Boot** (Web, JPA, Security)
* **JWT (JSON Web Token)** for authentication
* **PostgreSQL (Neon DB)** as database
* **Maven** for dependency management
* **Back4App** for hosting

---

## Setup & Installation

### Prerequisites

* Java 25
* Maven
* PostgreSQL (local or Neon DB)

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/jetly-backend.git
   cd jetly-backend
   ```

2. Configure environment variables in `.env` or `application.properties`:

   ```properties
   spring.datasource.url=${DATABASE_URL}
   spring.datasource.username=${DATABASE_USERNAME}
   spring.datasource.password=${DATABASE_PASSWORD}
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true

   jwt.secret=your_jwt_secret_key
   ```

3. Build and run the app:

   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

4. The backend will be available at:

   ```
   http://localhost:8080
   ```

---

## API Endpoints (Examples)

### Authentication

* `POST /api/auth/register` – Register a new user
* `POST /api/auth/login` – Login and receive JWT token

### URL Management

* `POST /api/urls/shorten` – Shorten a URL (requires JWT)
* `GET /{shortCode}` – Redirect to the original URL
* `GET /api/urls/totalClicks?startDate=YYYY-MM-DD&endDate=YYYY-MM-DD` – Get analytics

---

## Deployment

The backend is hosted on **Back4App** and connected to **Neon DB** for production usage.

---

## License

This project is licensed under the MIT License.
