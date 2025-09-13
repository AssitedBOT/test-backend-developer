---

# Backend Developer Skill Test

## Overview

This test evaluates your ability to build secure, efficient, and well-structured backend systems. You will work with REST APIs, WebSockets, FastAPI/Node.js, caching, database design, and external API integration.

---

## Tasks

1. **User Management API (CRUD + JWT)**
   Build a RESTful API to manage users (create, read, update, delete) with JWT authentication.

2. **WebSocket Notifications**
   Add WebSocket support to notify clients in real time when a user is created or updated.

3. **Framework Choice (FastAPI or Node.js)**
   Implement the API using either FastAPI or Node.js (Express).
   Explain your choice and compare with the alternative.

4. **Crypto Price Fetching (Binance API + WebSocket)**

   * Fetch live crypto prices (e.g., BTC/USDT) from Binance **REST API** and update your database every minute.
   * Subscribe to Binance **WebSocket stream** for real-time price updates and push them to your system.
   * Store the data in SQL/NoSQL of your choice.

5. **Frontend Integration**
   Provide an endpoint that returns user data together with the latest crypto price.

6. **Caching with Redis**
   Cache crypto prices in Redis with a TTL to minimize direct Binance requests.

7. **Database & Architecture Design**
   Design schemas for users and trades.
   Show both Monolithic and Microservices approaches, with pros/cons, and choose the most suitable.

8. **Internal API Service**
   Build an internal API that fetches crypto prices (via Binance API & WebSocket) and serves them to other internal services.
   Secure it with authentication.

9. **Project Structure**
   Deliver your project with a **clear and maintainable structure**.
   You must define and organize:

   * Application source code (APIs, services, database, caching, etc.)
   * Unit and integration tests
   * Documentation (README, Swagger/OpenAPI, Postman collection)
   * Deployment files (e.g., Docker, configs)

   *Note:* You are required to propose and implement your own project structure.

---

## Requirements

* **Deployment:** Deploy to cloud (Heroku, AWS, Vercel, etc.) and provide live URL.
* **Postman Collection:** Include requests/responses for API testing.
* **Documentation:** Use `README.md` or Swagger/OpenAPI docs. Provide a link.
* **Testing:** Write unit tests and include them in the repository.
* **Project Structure:** Must be well-organized and follow best practices.

---

## Evaluation Criteria

* Code quality & best practices
* Correctness & completeness
* Performance & caching efficiency
* Documentation clarity
* Test coverage & reliability
* Project structure & maintainability
* Creativity & extra features

---

📧 Submit to: **[nanobotsup@gmail.com](mailto:nanobotsup@gmail.com)**
Good luck! 🚀

---
