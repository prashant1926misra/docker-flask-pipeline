# CI/CD Pipeline with Dockerized Python App on AWS ECS


## Project Overview
This project demonstrates an end-to-end CI/CD pipeline for a containerized Python application. The pipeline automatically builds, tests, and deploys a Dockerized Python app to AWS ECS (Fargate) using GitHub Actions. Python is used both for the application itself and for automation scripts.


## Workflow Diagram

```text
GitHub Repository (Python App + Workflow)
           │
           ▼
   GitHub Actions Workflow
      - Run Unit Tests
      - Build Docker Image
      - Push Image to AWS ECR
      - Update ECS Service (Fargate)
           │
           ▼
     AWS ECS Fargate Service
           │
           ▼
   Python Validation Script
      → Calls ECS App Endpoint
      → Returns Health Status
```


## Tools & Concepts Used
- ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?logo=github-actions&logoColor=white)  
  CI/CD → workflows, jobs, secrets management  
- ![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)  
  Containerization → build, push image to AWS ECR  
- ![Amazon ECS](https://img.shields.io/badge/AWS_ECS-Fargate-FF9900?logo=amazon-aws&logoColor=white)  
  Cloud → ECS cluster/service, task definitions, IAM roles  
- ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)  
  Flask app and automation scripts


## Features
- Automated CI/CD pipeline with GitHub Actions  
- Containerized Python API deployed to AWS ECS  
- Health-check validation using Python requests  


## Repository Structure

```text
docker-flask-pipeline/
├── Dockerfile
├── app.py
├── requirements.txt
├── .github/
│   └── workflows/
│       └── ci.yml
├── infra/
│   └── task-definition.json
├── tests/
│   ├── test_app.py
│   └── validate.py
└── README.md
```


## Screenshots 

### GitHub Actions Workflow Run
<img width="979" height="466" alt="image" src="https://github.com/user-attachments/assets/848f8417-e1a1-4005-81ff-b0e92cafa865" />
<img width="979" height="242" alt="image" src="https://github.com/user-attachments/assets/fde7bff7-525a-4cbc-90df-4ea40d4a39ad" />

### Python Validation
<img width="979" height="439" alt="image" src="https://github.com/user-attachments/assets/a0e031f5-b586-493a-a5ca-6dcedd08ec93" />

### ECS Service Overview
<img width="979" height="402" alt="image" src="https://github.com/user-attachments/assets/d64fc385-8e15-4313-9df2-343351b209d6" />

### ECR Repository
<img width="979" height="228" alt="image" src="https://github.com/user-attachments/assets/ed3d9021-f190-448d-b177-0c27ac33cfcc" />


## Key Learnings
- How to integrate **CI/CD, Docker, and AWS ECS** into one workflow  
- Using **Python as glue** for validation and automation
- Understanding core AWS ECS concepts: ECR, task definitions, Fargate service
