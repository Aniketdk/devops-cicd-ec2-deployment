🚀 DevOps CI/CD Pipeline with Docker & AWS EC2

This project demonstrates an end-to-end CI/CD pipeline using GitHub Actions, Docker, DockerHub, and AWS EC2. 
The application is automatically built, pushed to DockerHub, and deployed to an EC2 instance on every push to the main branch.

📌 Project Overview

This project automates:

Building Docker image

Pushing image to DockerHub

Connecting to EC2 via SSH

Pulling latest Docker image

Running container automatically

The application becomes live at: http://43.205.237.47:3000

🛠️ Tech Stack

Git & GitHub

GitHub Actions (CI/CD)

Docker

DockerHub

AWS EC2 (Linux)

WSL (for local development)

🔄 CI/CD Workflow Architecture
Developer → GitHub Push → GitHub Actions
            ↓
      Build Docker Image
            ↓
      Push to DockerHub
            ↓
      SSH into EC2
            ↓
   Pull Latest Docker Image
            ↓
      Run Docker Container

📂 Project Structure
.
├── .github/workflows/
│   └── ci-cd.yml
├── Dockerfile
├── package.json
├── app.js (or main application file)
└── README.md

⚙️ GitHub Secrets Used

The following secrets are configured in GitHub:

Secret Name              	Description
DOCKER_USERNAME	      DockerHub username
DOCKER_PASSWORD	      DockerHub access token
HOST	                EC2 Public IP
USERNAME	            EC2 username (ubuntu / ec2-user)
KEY	                  Private SSH key

🐳 Docker Commands Used

Build image locally:
docker build -t aniketdk/devops-app:latest .

Push image:
docker push aniketdk/devops-app:latest

Run container:
docker run -d -p 3000:3000 --name cicd-container aniketdk/devops-app:latest

🖥️ EC2 Setup

EC2 Instance (Ubuntu)

Security Group allowing:
Port 22 (SSH)
Port 3000 (Application)
Docker installed on EC2

🔐 Security Configuration

SSH key-based authentication
DockerHub access token used instead of password
EC2 Security Group configured properly

📈 Features

✔ Automated CI/CD pipeline
✔ Zero manual deployment
✔ Dockerized application
✔ Cloud deployment using AWS
✔ Production-style workflow

🚀 Future Improvements

Add Nginx reverse proxy.
Add HTTPS using Let's Encrypt.
Use Docker Compose.
Deploy using Kubernetes (EKS)
Add monitoring (Prometheus & Grafana)
Infrastructure as Code using Terraform.
