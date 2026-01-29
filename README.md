# Secure Kubernetes Todo Application  
## CI/CD + Monitoring (K3s Based Implementation)

---

## 📌 Project Overview

This project implements a **secure, production-style Kubernetes deployment** of a Todo application using **K3s**.  
It integrates **CI/CD**, and **monitoring**.


---

## 🧱 System Architecture Overview

### Core Components
- **CI/CD Pipeline**: Jenkins, SonarQube, Trivy
- **Application Stack**: Flask Todo App + MySQL
- **Monitoring**: Prometheus + Grafana
- **Platform**: K3s Kubernetes Cluster

---

## 🔁 CI/CD Pipeline Architecture

### Tools Used
- **Jenkins** – Continuous Integration
- **SonarQube** – Static code analysis
- **Docker** – Image build
- **Trivy** – Container vulnerability scanning

### Workflow
1. Source code pushed to GitHub
2. Jenkins pipeline triggered
3. SonarQube scans code quality
4. Docker image is built
5. Trivy scans image for CVEs
6. Secure image is deployed to Kubernetes

---

## ☸️ Kubernetes Cluster Design

### Namespace: `todo`

All application and security workloads run inside the `todo` namespace (except monitoring).

---

## 🧩 Application Components

### Todo Application
- Flask-based web application
- Deployed with multiple replicas
- Uses:
  - **Secrets** for database credentials
  - **ConfigMaps** for database initialization
- Exposed using **NodePort service**

### MySQL Database
- MySQL 8.0 deployment
- Persistent storage using PVC
- Initialization SQL loaded via ConfigMap
- Internal ClusterIP service

---

## 🔐 Secrets & Configuration Management

### Kubernetes Secrets
- Database credentials
- Application secret key

### ConfigMaps
- MySQL database initialization scripts
- Application configuration (if required)

---


