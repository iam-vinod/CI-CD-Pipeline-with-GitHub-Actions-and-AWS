# CI-CD-Pipeline-with-GitHub-Actions-and-AWS

**Overview**

This project implements a CI/CD pipeline using GitHub Actions to automate the deployment of a Flask application to an AWS EC2 instance. The pipeline builds a Docker image, pushes it to DockerHub, and deploys it to the EC2 instance using SSH.

**Tech Stack Used**

*GitHub Actions – Automates CI/CD pipeline

*Docker – Containerizes the Flask application

*DockerHub – Stores and distributes the Docker image

*AWS EC2 – Hosts the application

*Flask – Lightweight Python web framework

*Gunicorn – WSGI server for running Python applications

**How It Works**

1. Code Push: Developer pushes code to the main branch on GitHub.
2. GitHub Actions: Triggers a workflow that:

Checks out the repository

Builds a Docker image

Pushes the image to DockerHub

Logs into the EC2 instance and pulls the latest Docker image

Runs the container on EC2

3. Deployment: The Flask application is now live on the EC2 instance and accessible via its public IP.

**Deployment**

1. **Ensure AWS EC2 Instance is Set Up
**
Install Docker: sudo apt update && sudo apt install docker.io -y

Start Docker: sudo systemctl start docker && sudo systemctl enable docker

2. **Set Up GitHub Secrets:**

DOCKER_USERNAME – DockerHub username

DOCKER_PASSWORD – DockerHub password

EC2_PUBLIC_IP – Public IP of AWS EC2 instance

EC2_USER – SSH username (e.g., ubuntu)

EC2_PRIVATE_KEY – Private key for SSH access

3. **Trigger Deployment**

Push changes to the main branch:

git add .
git commit -m "Updated code"
git push origin main

GitHub Actions will automatically execute the workflow.

4. **Verify Deployment**

Open a browser and visit http://<EC2_PUBLIC_IP> to see the running Flask app.
