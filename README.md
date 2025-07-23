# 🏋️‍♂️ Fitness AI Platform

### 🔥 A Full Stack Intelligent Fitness Web App built with:

- 🧰 Spring Boot Microservices (6 Services)
- 🌐 Eureka Server & Config Server (Service Discovery & Central Config)
- 🛡️ Keycloak (OAuth2 SSO Authentication via Docker)
- 📩 RabbitMQ (Asynchronous Messaging)
- ⚛️ React.js (Frontend SPA)
- 🤖 Gemini AI (Google GenAI API for Smart Recommendations)
- 🐳 Docker (Microservice Containerization)

---

## 🚀 Project Overview

**Fitness AI Platform** is a modular and containerized full-stack fitness application where users can sign up, log in securely using Keycloak SSO, and track their fitness activities like walking, running, cycling, etc. The app intelligently provides AI-powered health suggestions using **Google Gemini API**, making the experience personalized and smart.

The backend is built using **Java Spring Boot microservices** and the frontend is developed in **React.js**. All services are containerized using Docker and managed via centralized configuration and service discovery.

---

## 🧱 Project Architecture

"# SpringBoot-AI-Microservices" 

   
                      ┌──────────────────────┐
                      │     React Frontend   │
                      │ (Login / Activities) │
                      └─────────┬────────────┘
                                │
                                ▼
                     ┌────────────────────────┐
                     │     API Gateway        │
                     │ (Keycloak + Routing)   │
                     └─────┬──────────┬───────┘
                           │          │
                           ▼          ▼
          ┌────────────────────┐  ┌─────────────────────┐
          │  User Service      │  │  Activity Service   │
          │ (User mgmt + DB)   │  │ (Add  Activities)   │
          └──────┬─────────────┘  └─────────┬───────────┘
                 │                          │
                 ▼                          ▼
      ┌────────────────────┐     ┌────────────────────┐
      │ PostgreSQL         │     │ RabbitMQ Broker    │
      └────────────────────┘     └────────────────────┘
                                         │
                                         ▼
                               ┌─────────────────────┐
                               │     AI Service      │
                               │ (Gemini API calls)  │
                               └─────────────────────┘
                                         │
                                         ▼
                               ┌─────────────────────┐
                               │ Gemini API (GenAI)  │
                               └─────────────────────┘

       ┌───────────────┐      ┌────────────────────┐
       │ Eureka Server │◄────▶ All Microservices  |
       └───────────────┘      └────────────────────┘

       ┌────────────────────┐
       │ Config Server      │
       │ Central .yml config│
       └────────────────────┘

       ┌────────────────────┐
       │ Docker Containers  │
       │ (All services)     │
       └────────────────────┘

       ┌────────────────────┐
       │ Docker Containers  │
       │ (All services)     │
       └────────────────────┘


## 🧠 Gemini AI Integration
The **AI microservice** connects with **Google's Gemini API** to generate smart, real-time health suggestions based on user activity patterns.  
Examples of Gemini-powered outputs:
- “You walked 1.2 km today. Great job! Let’s aim for 1.5 km tomorrow.”
- “You’ve been inactive for 3 days. Try 10 mins of stretching today.”

This makes the app proactive, intelligent, and engaging.

## 🧩 Microservices Breakdown

| Service            | Role                                                                    |
|--------------------|-------------------------------------------------------------------------|
| **Eureka Server**   | Service discovery and registration                                     |
| **Config Server**   | Centralized configuration for all services                             |
| **User Service**    | Handles user registration, login data, stores info in PostgreSQL       |
| **Activity Service**| Manages fitness activities (e.g., walk, run, cycle), sends to RabbitMQ |
| **AI Service**      | Connects to Gemini API and gives personalized fitness suggestions      |
| **Gateway Service** | Routes all APIs + handles Keycloak-based authentication (OAuth2)       |

---

## 🧑‍💻 Tech Stack

| Layer      | Technology Used                                      |
|------------|------------------------------------------------------|
| Frontend   | React.js, Axios, Bootstrap/CSS                       |
| Backend    | Java 17+, Spring Boot, Spring Cloud, Spring Security |
| Messaging  | RabbitMQ                                             |
| AI         | Gemini API (Google Generative AI)                    |
| Auth       | Keycloak (OAuth2 SSO), Dockerized                    |
| Databases  | PostgreSQL (User), MongoDB (optional)                |
| DevOps     | Docker, Docker Compose                               |
| Config/Registry | Spring Cloud Config & Eureka Server             |

---
## 🚀 Frontend Tech Stack

The frontend of this project is built using **React.js** and includes the following libraries/tools:
```
- 🔁 **React Redux** – For state management  
- 🧰 **Redux Toolkit** – Simplified Redux logic and store setup  
- 🧭 **React Router** – For client-side routing  
- 🎨 **Material UI (MUI)** – For modern, responsive UI components  
- 🔐 **React OAuth2 Code PKCE** – Secure OAuth2 login flow  
- 📡 **Axios** – For making API requests
```

## 🔐 Authentication (Keycloak)

- Deployed using Docker container.
- Keycloak handles all user login/logout + token-based SSO.
- Gateway Service protects APIs using Spring Security & JWT from Keycloak.
- Role-based access control supported.

---

## 📦 How to Run the Project

### 📌 Prerequisites:

- Java 17+
- Node.js 18+
- Docker & Docker Compose
- RabbitMQ
- Keycloak Docker Image
- Gemini API Key from Google AI Studio

Frontend
```
cd frontend
npm install
npm start
```




---

## ✍️ Author

**👨‍💻 Piyush Pal**  
📍 Dewas, Indore, Madhya Pradesh  
📫 thepeeyushyadav0@gmail.com 

🔗 https://www.linkedin.com/in/piyush-pal-751067306?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app

🎥 https://youtube.com/@thinkcodex?si=WlZD5b1neipAHXcR
