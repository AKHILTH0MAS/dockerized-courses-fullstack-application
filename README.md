# 📦 Full Stack Courses — Containerized Deployment (PERN)

This project is a Dockerized version of the original **Full Stack Courses** application, built using the **PERN stack (PostgreSQL, Express, React, Node.js)**.

No core application logic was changed — the focus of this version is **improving developer experience, deployment, and portability** using Docker and Docker Compose.

---

## 🧱 Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | React (Vite) |
| Backend | Node.js + Express |
| ORM | Sequelize |
| Database | PostgreSQL |
| Containerization | Docker + Docker Compose |

---

## 🧩 What’s Included

This release introduces full containerization:

- `Dockerfile` for backend
- `Dockerfile` for frontend
- `docker-compose.yml` orchestrating:
  - Backend API container
  - Frontend container
  - PostgreSQL database container

With this setup, the **entire project can run with a single command**.

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```sh
git clone https://github.com/AKHILTH0MAS/dockerized-courses-fullstack-application.git
cd dockerized-courses-fullstack-application
```
### 2️⃣ Start the stack
```sh
docker compose up --build
```
Once running, access the services at:

#### Service Url
```sh
Frontend	http://localhost:3000
Backend API	http://localhost:4000
Swagger Docs	http://localhost:4000/api/docs
```
#### 📂 Project Structure
```bash
📦 fullstack-courses
 ┣ 📁 client
 ┃ ┗── Dockerfile
 ┣ 📁 server
 ┃ ┗── Dockerfile
 ┣── docker-compose.yml
 ┣── README.md
 ┗── ...
 ```
#### 📝 Features

* Create new courses
* Read all courses or fetch one by ID
* Update course details
* Delete a course
* Search & filter UI on frontend
#### 🎯 Why Containerization?

##### Running the original project required multiple terminal windows, database installation, migrations, and environment setup. Docker fixes that by providing:
* Consistent environment across systems
* No local PostgreSQL setup required
* Faster onboarding for contributors
* Deployment-ready architecture
* Works cleanly with CI/CD pipelines and Kubernetes

#### 🔧 Future Enhancements
* Multi-stage Docker builds for production
* Persistent PostgreSQL storage via named volumes
* GitHub Actions CI pipeline
* Helm chart deployment for Kubernetes

