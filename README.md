# Credit Score Analysis Tool (Microservices Architecture)

A full microservices-based Credit Score Analysis system built using **Spring Boot**, **Kafka**, **Redis**, **MySQL**, and **Docker Compose**, with an API Gateway for unified routing. The platform simulates a real-world fintech system for user management, credit scoring, notification handling, and more.

---

## 🚀 Architecture Overview

This project is designed using a **production-style microservices architecture**, including:

### **1. User Management Service (Spring Boot)**
- User registration & login  
- Password encryption (BCrypt)  
- JWT authentication  
- MySQL database  
- REST APIs for user identity  

### **2. Credit Score Service**
- Generates credit scores  
- Stores history in MySQL  
- Communicates with User Service  
- Kafka producer/consumer for async scoring  
- Redis caching for fast data retrieval  

### **3. API Gateway (Spring Cloud Gateway)**
- Central routing for all microservices  
- CORS, security, and request forwarding  
- Unified API endpoint: `/api/...`

### **4. Infrastructure**
- **Kafka** → async communication  
- **Redis** → caching  
- **Docker Compose** → one‑command deployment  
- **MySQL containers** → isolated persistent storage  

---

## 🛠️ Tech Stack

| Component | Technology |
|----------|------------|
| Backend | Java 17, Spring Boot 3 |
| Messaging | Apache Kafka / Redpanda |
| Cache | Redis |
| Auth | Spring Security, JWT |
| Database | MySQL |
| DevOps | Docker, Docker Compose |
| Communication | REST, WebClient |

---

## 📦 How to Run the Project

### **1️⃣ Clone the repository**
```bash
git clone https://github.com/Tejas111296/CreditScoreAnalysisTool.git
cd CreditScoreAnalysisTool
```

### **2️⃣ Start all microservices**
```bash
docker compose up --build
```

### **3️⃣ Verify services**
```bash
curl http://localhost:8080/api/users/actuator/health
curl http://localhost:8080/api/credit/actuator/health
```

---

## 📌 Example API Calls

### **Register User**
```bash
POST /api/users/register
```

### **Login User**
```bash
POST /api/users/login?username=john&password=123
```

### **Fetch Credit Score**
```bash
GET /api/credit/score/{userId}
```

---

## 🎯 Core Features

- Microservices‑based architecture  
- Secure JWT authentication  
- Kafka event-driven communication  
- Redis caching  
- Docker-based deployment  
- Realistic fintech simulation  

---

## 📁 Folder Structure

```
CreditScoreAnalysisTool
│── cloudgateway/
│── credit/
│── userms/
│── docker-compose.yml
└── README.md
```

---

## ⚠️ Current Status

This project is a **work in progress**.

- ✅ Docker Compose spins up all services (gateway, user service, credit service, Kafka, Redis, MySQL)
- ✅ User registration is working
- ✅ Actuator health checks are working through the gateway
- ⚠️ `/users/login` endpoint is under active debugging (returns 500 in the current version)
- 🔜 Next steps: finalize JWT auth flow and secure credit APIs end-to-end

---

## 👤 Author

**Tejas Tondase**  
Cloud | DevOps | Java Developer  
GitHub: https://github.com/Tejas111296  

---

## 📝 License
MIT License  
