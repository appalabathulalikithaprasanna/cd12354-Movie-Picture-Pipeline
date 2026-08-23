# Movie Picture Pipeline

## Project Overview

The Movie Picture Pipeline is a full-stack web application that demonstrates how to build, containerize, test, and continuously deploy a frontend and backend application using modern DevOps and cloud technologies.

The project consists of:

- A React frontend for displaying movie information.
- A Python Flask backend that provides REST API endpoints for movie data.
- Docker containers for packaging the frontend and backend applications.
- Amazon Elastic Container Registry (ECR) for storing Docker images.
- Amazon Elastic Kubernetes Service (EKS) for running the application containers.
- Kubernetes Deployments and Services for managing application workloads and networking.
- GitHub Actions for Continuous Integration and Continuous Deployment (CI/CD).

The project demonstrates an automated workflow from source code changes to application deployment on Kubernetes.

---

## Architecture

```text
                         GitHub Repository
                               |
                               |
                    +----------+----------+
                    |                     |
              Frontend CI/CD          Backend CI/CD
                    |                     |
                    v                     v
              Docker Build           Docker Build
                    |                     |
                    v                     v
              Amazon ECR             Amazon ECR
              Frontend Image         Backend Image
                    |                     |
                    +----------+----------+
                               |
                               v
                         Amazon EKS
                               |
                    +----------+----------+
                    |                     |
                    v                     v
              Frontend Pod           Backend Pod
              Port 3000              Port 5000
                    |                     |
                    v                     v
              NodePort 30080         NodePort 30647
                    |                     |
                    +----------+----------+
                               |
                               v
                         Web Browser