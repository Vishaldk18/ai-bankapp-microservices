# 🏦 AI Bank Application (Dockerized with Ollama)

## 📌 Overview

This project is a **production-grade AI-powered banking application** built using a microservices architecture. It integrates a backend service with a database and a local LLM (Large Language Model) using Ollama.

The entire system is containerized using Docker Compose for easy setup and deployment.

---

## 🧰 Tech Stack

* ☕ Java (Spring Boot)
* 🐳 Docker & Docker Compose
* 🗄️ MySQL 8.0
* 🤖 Ollama (LLM Runtime)
* 🧠 TinyLlama Model
* 🔐 DevSecOps Best Practices

---

## 🏗️ Architecture

```
User → BankApp (Spring Boot)
              → MySQL Database
              → Ollama (TinyLlama LLM)
```

---

## ⚙️ Services

### 🗄️ MySQL

* Stores application data
* Persistent storage using Docker volume
* Health checks enabled

### 🤖 Ollama

* Runs local LLM
* Provides AI-powered responses

### 🧠 Model Loader

* Automatically pulls `tinyllama` model
* Ensures model availability before app starts

### 🚀 BankApp

* Core backend service
* Connects to MySQL and Ollama

---

## 📁 Project Structure

```
ai-bankapp/
│
├── docker-compose.yml
├── Dockerfile
├── .dockerignore
├── .gitignore
├── README.md
│
├── src/
├── pom.xml
└── mvnw
```

---

## 🚀 Getting Started

### 1️⃣ Clone Repository

```bash
git clone https://github.com/vishaldk18/ai-bankapp-docker-ollama.git
cd ai-bankapp-docker-ollama
```

### 2️⃣ Start Application

```bash
docker compose up -d
```

### 3️⃣ Verify Containers

```bash
docker ps
```

### 4️⃣ Access Application

```
http://localhost:8080
```

---

## 🐳 Docker Build (Manual)

### Build Image

```bash
docker build -t ai-bankapp .
```

### Run Container

```bash
docker run -p 8080:8080 ai-bankapp
```

---

## 🔍 Health Checks

* MySQL → `mysqladmin ping`
* Ollama → `ollama list`
* App starts only after dependencies are healthy

---

## 🔐 Environment Variables

| Variable       | Description         |
| -------------- | ------------------- |
| MYSQL_HOST     | mysql               |
| MYSQL_PORT     | 3306                |
| MYSQL_DATABASE | bankappdb           |
| MYSQL_USER     | root                |
| MYSQL_PASSWORD | password            |
| OLLAMA_URL     | http://ollama:11434 |

---

## 📦 Volumes

* `mysql-data` → persists database
* `ollama-data` → stores AI models

---

## 🧹 Stop Application

```bash
docker compose down
```

---

## 💡 Key Features

* ✅ Multi-container architecture using Docker Compose
* ✅ AI integration using Ollama (TinyLlama)
* ✅ Automated model download
* ✅ Health checks & service dependencies
* ✅ Persistent storage with volumes
* ✅ Secure Dockerfile (non-root user, Alpine base)

---

## 🔐 Security Best Practices

* Non-root container execution
* Minimal base image (Alpine)
* Reduced CVE exposure
* Multi-stage Docker build

---

## 📚 Learnings

* Docker multi-stage builds
* Service orchestration using Docker Compose
* AI integration in backend systems
* DevSecOps fundamentals
* Container security best practices

---

## 🚀 Future Improvements

* CI/CD pipeline using GitHub Actions
* Deployment on AWS (ECS / EKS)
* Add NGINX reverse proxy
* Monitoring with Prometheus & Grafana

---

## 👨‍💻 Author

**Vishal Khairnar**
Cloud & DevOps Engineer 🚀

---

## ⭐ Support

If you like this project, give it a ⭐ on GitHub!

