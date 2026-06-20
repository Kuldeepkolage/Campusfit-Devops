# 🚀 CampusFit DevOps Project

A production-style DevOps project demonstrating containerization, orchestration, and CI/CD automation using Node.js, MongoDB, Docker, Kubernetes, Jenkins, and Docker Hub.

---

## 📌 Project Overview

CampusFit is a student registration application built with Node.js and MongoDB.

This project was transformed from a simple local application into a fully containerized and automated deployment pipeline using modern DevOps practices.

### Features

* Student Registration API
* MongoDB Database Integration
* Docker Containerization
* Docker Compose Multi-Container Setup
* Kubernetes Deployment
* ConfigMaps & Secrets
* Health Checks (Liveness & Readiness Probes)
* Jenkins CI/CD Pipeline
* Docker Hub Integration
* Automated Kubernetes Deployments

---

## 🏗️ Architecture

GitHub Repository
↓
Jenkins Pipeline
↓
Docker Build
↓
Docker Hub
↓
Kubernetes Deployment
↓
Application Verification

---

## 🛠️ Tech Stack

### Backend

* Node.js
* Express.js
* MongoDB
* Mongoose

### DevOps

* Docker
* Docker Compose
* Kubernetes
* Minikube
* Jenkins
* Docker Hub

---

## 📂 Project Structure

Campusfit-Devops/

├── app.js

├── package.json

├── Dockerfile

├── docker-compose.yml

├── Jenkinsfile

├── .env.example

├── k8s/

│ ├── app-deployment.yaml

│ ├── app-service.yaml

│ ├── mongodb-deployment.yaml

│ ├── mongodb-service.yaml

│ ├── mongodb-secret.yaml

│ └── app-configmap.yaml

├── controllers/

├── models/

├── routes/

└── config/

---

## 🚀 Local Development

### Install Dependencies

npm install

### Configure Environment

cp .env.example .env

### Start Application

npm start

---

## 🐳 Docker Setup

### Build Image

docker build -t campusfit-app .

### Run Container

docker run -p 3000:3000 campusfit-app

### Docker Compose

docker-compose up -d

---

## ☸️ Kubernetes Deployment

### Apply Kubernetes Resources

kubectl apply -f k8s/

### Verify Deployment

kubectl get deployments

kubectl get pods

kubectl get services

### Access Application

minikube service campusfit-service --url

---

## 🔄 Jenkins CI/CD Pipeline

Pipeline Stages:

### Stage 1 – Checkout

Pull latest code from GitHub.

### Stage 2 – Build

Build Docker image.

### Stage 3 – Push

Push image to Docker Hub.

### Stage 4 – Deploy

Update Kubernetes deployment.

### Stage 5 – Verify

Validate deployment status and pod health.

---

## 📡 API Endpoints

### Health Check

GET /health

Example:

curl http://localhost:3000/health

### Register Student

POST /student

Example:

curl -X POST http://localhost:3000/student 
-H "Content-Type: application/json" 
-d '{"name":"Kuldeep","membership":"Premium"}'

Membership Types:

* Basic
* Premium
* Elite

---

## 🧪 Testing

Run API tests:

chmod +x test-api.sh

./test-api.sh

---

## 📊 Kubernetes Features Implemented

* Deployments
* Services
* ConfigMaps
* Secrets
* Resource Limits
* Resource Requests
* Liveness Probes
* Readiness Probes
* Rolling Updates

---

## 🔐 Security Features

* Kubernetes Secrets for credentials
* Environment Variable Management
* Docker Hub Credential Integration with Jenkins

---

## 🎯 Learning Outcomes

Through this project I learned:

* Docker Containerization
* Multi-Container Applications
* Docker Networking
* Docker Hub Image Management
* Kubernetes Deployments
* Kubernetes Services
* ConfigMaps & Secrets
* Health Monitoring
* Jenkins CI/CD Pipelines
* Automated Deployments
* DevOps Troubleshooting

---

## 👨‍💻 Author

Kuldeep Kolage

DevOps | Full Stack Development | Cloud & Infrastructure Learning

---

⭐ If you found this project useful, consider giving it a star.
