# Expense Tracking System – Microservices

A **Spring Boot–based Expense Tracking System** built using **microservices architecture**, **MySQL**, **Apache Kafka**, and **Docker**.  
The application enables secure user authentication, expense management, and asynchronous communication between services.

---

## 🧩 Services Summary

### 🔐 Auth Service
- Handles **user registration and authentication**
- Publishes **user-related events** to Kafka
- Acts as the **event producer**
- Uses MySQL for persistence

**Responsibilities**
- User signup / login
- Publish `UserInfoEvent` to Kafka topic

---

### 👤 User Service
- Manages **user profile information**
- Consumes Kafka events from Auth Service
- Keeps user data synchronized asynchronously

**Responsibilities**
- Create/update user profile
- Consume user events from Kafka

---

### 💰 Expense Service
- Manages **expense-related operations**
- Stores and retrieves expense records
- Linked to users via user ID

**Responsibilities**
- Add, update, delete expenses
- Fetch expenses per user
- Categorize and manage expense history

---

### 📊 (Optional) Notification / Analytics Service
- Kafka consumer service
- Processes events asynchronously
- Used for analytics or notifications

**Responsibilities**
- Listen to Kafka events
- Perform background processing



