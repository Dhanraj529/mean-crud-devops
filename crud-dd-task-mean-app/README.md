🚀 MEAN Stack Application – Deployment Flow & Execution Summary

This project demonstrates the end-to-end containerization, CI/CD automation, and cloud deployment of a full-stack MEAN (MongoDB, Express, Angular, Node.js) application using modern DevOps practices.

The assignment focuses on implementing a scalable, container-based architecture deployed on a cloud-hosted Ubuntu virtual machine with automated build and deployment pipelines.


🏗️ Application Architecture

The application follows a reverse-proxy based containerized architecture:

User Request → Nginx (Port 80) → Frontend (Angular) → Backend API (Node.js / Express) → MongoDB

Nginx acts as the single entry point, routing client requests to appropriate services:

• Root requests ( / ) → Frontend Application
• API requests ( /api ) → Backend Service

All components run as isolated Docker containers orchestrated through Docker Compose.



📦 Containerization Strategy

Each layer of the application was containerized to ensure portability, scalability, and environment consistency:

• Frontend container serving the Angular application
• Backend container running Node.js / Express API
• MongoDB container providing persistent data storage
• Nginx container handling reverse proxy and request routing

Docker Compose was used to manage inter-container networking and service dependencies.



☁️ Cloud Deployment Environment

The application was deployed on an Ubuntu-based cloud virtual machine (AWS EC2 instance).

Deployment setup included:

• Provisioning of Ubuntu EC2 instance
• Installation of Docker Engine
• Installation of Docker Compose
• Pulling Docker images from Docker Hub
• Multi-container application launch

The cloud VM serves as the runtime infrastructure for the containerized application.


🔁 CI/CD Automation Flow

A CI/CD pipeline was implemented using GitHub Actions to automate build and deployment processes.

Pipeline execution flow:

Developer pushes code changes to GitHub repository

GitHub Actions workflow is triggered automatically

Docker images are built for frontend and backend

Newly built images are pushed to Docker Hub

Cloud VM pulls updated images

Containers are restarted with latest versions

This ensures continuous integration and automated delivery without manual intervention.

🌐 Reverse Proxy & Traffic Routing

Nginx was configured as a reverse proxy to expose the application through a single public access point.

Responsibilities of Nginx:

• Listen on Port 80
• Route UI traffic to Frontend Container
• Route API traffic to Backend Container
• Provide centralized request handling

This setup enables clean separation of services while maintaining unified user access.

🚀 Execution & Deployment Commands Used

The following commands were primarily used during setup and deployment:

Repository & Source Control:

• Cloning GitHub repository
• Committing and pushing code changes

Docker Operations:

• Building Docker images
• Tagging Docker images
• Pushing images to Docker Hub
• Pulling images from Docker Hub

Container Orchestration:

• Starting multi-container services
• Running containers in detached mode
• Stopping containers
• Restarting containers

Cloud VM Setup:

• Connecting to EC2 instance via SSH
• Installing Docker Engine
• Installing Docker Compose
• Verifying running containers

Monitoring & Verification:

• Listing active containers
• Checking container logs
• Validating service accessibility

✅ Deployment Outcome

The final deployment delivers:

✔ Fully containerized MEAN stack application
✔ Automated CI/CD workflow
✔ Cloud-hosted runtime environment
✔ Reverse proxy based routing
✔ Unified access via Port 80

The system ensures portability, reproducibility, and automated delivery aligned with modern DevOps practices.

🌍 Application Access

The deployed application is accessible through:

Public IP of Cloud VM → Port 80

This provides direct user access to the application interface via the Nginx reverse proxy.

