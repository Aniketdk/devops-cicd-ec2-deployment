# 🚀 CI/CD Pipeline Deployment using Docker & AWS EC2

## 📌 Project Overview

This project implements a complete end-to-end CI/CD pipeline that automatically builds, pushes, and deploys a Dockerized application to an AWS EC2 instance using GitHub Actions.

Every push to the `main` branch triggers an automated workflow that deploys the latest version of the application to production without manual intervention.

---

## 🏗️ Architecture Flow

Developer Push → GitHub → GitHub Actions  
→ Build Docker Image  
→ Push to DockerHub  
→ SSH into EC2  
→ Pull Latest Image  
→ Restart Container  
→ Application Live

---

## 🛠️ Tech Stack

- Git & GitHub
- GitHub Actions (CI/CD)
- Docker
- DockerHub
- AWS EC2 (Linux)
- WSL (Local Development)

---

## ⚙️ Automated Workflow

On every code push:

1. Docker image is built.
2. Image is pushed to DockerHub.
3. GitHub Actions connects to EC2 via SSH.
4. Existing container is stopped and removed.
5. Latest image is pulled.
6. New container is deployed automatically.

---

## 🔐 Secure Configuration

GitHub Secrets Used:
- DOCKER_USERNAME
- DOCKER_PASSWORD (Access Token)
- HOST (EC2 Public IP)
- USERNAME (ubuntu / ec2-user)
- KEY (Private SSH Key)

Security Group Configuration:
- Port 22 (SSH)
- Port 3000 (Application)

---

## 🌐 Live Deployment

Application accessible at:

http://43.205.237.47:3000
---

## 📈 DevOps Concepts Demonstrated

- CI/CD Automation
- Docker Containerization
- Cloud Deployment (AWS EC2)
- Secure Credential Management
- SSH-based Remote Deployment
- Zero Manual Production Deployment

---

