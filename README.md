🚀 DevOps Modernization: Final Exam Project

Project Overview

This project demonstrates the containerization and automated deployment of a full-stack application consisting of a React + Vite frontend and a .NET 10 Web API backend. The goal was to move from a manual, error-prone process to a streamlined CI/CD pipeline.

Architecture
Frontend: React (Vite) served via Nginx.

Backend: .NET 10 REST API.

Reverse Proxy: Nginx is configured to route traffic to the appropriate container.

Infrastructure: AWS EC2 Instance (Ubuntu 24.04 LTS).

Orchestration: Docker Compose.

CI/CD Pipeline Workflow
I designed a GitHub Actions pipeline (deploy-qa.yml) that automates the following steps on every push to the main branch:

Build & Package: Automatically builds Docker images for both the frontend and backend.

Registry Push: Tags and pushes the images to Docker Hub.

Automated Deployment: * Logs into the AWS QA Server via SSH.

Pulls the latest images from Docker Hub.

Restarts the containers using docker compose to ensure the latest version is live.

Local Setup
To run this project locally for development:

PowerShell
docker compose up --build -d
The application will be available at http://localhost.

Deployment Verification
QA Environment: http://18.116.234.202

API Health Check: http://18.116.234.202/api/ping

Deployment Evidence: Successful pipeline runs and screenshots are located in the /screenshots directory.
