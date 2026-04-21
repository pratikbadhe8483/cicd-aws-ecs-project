# 🚀 CI/CD Pipeline for AWS ECS Deployment

## 📌 Project Overview

This project demonstrates an end-to-end CI/CD pipeline that automatically builds and deploys a Dockerized Node.js application to AWS ECS using AWS services.

The goal of this project is to automate application deployment using a scalable and production-ready DevOps workflow.

---

## 🏗️ Architecture

```
Developer → GitHub → CodePipeline → CodeBuild → Amazon ECR → ECS (Fargate) → Load Balancer → User
```

---

## 🛠️ Tech Stack

* AWS ECS (Fargate)
* AWS ECR (Elastic Container Registry)
* AWS CodePipeline
* AWS CodeBuild
* Docker
* Node.js
* Git & GitHub

---

## 🔄 CI/CD Workflow

1. Developer pushes code to GitHub
2. AWS CodePipeline detects changes
3. CodeBuild builds Docker image
4. Image is pushed to Amazon ECR
5. ECS service pulls latest image
6. Application is deployed via Load Balancer

---

## 📦 Project Structure

```
.
├── Dockerfile
├── buildspec.yml
├── app.js
├── html/
│   └── index.html
├── package.json
├── package-lock.json
└── README.md
```

---

## ⚙️ Setup & Installation

### 1️⃣ Clone the repository

```bash
git clone https://github.com/pratikbadhe8483/cicd-aws-ecs-project.git
cd cicd-aws-ecs-project
```

---

### 2️⃣ Build Docker Image

```bash
docker build -t nodejs-app .
```

---

### 3️⃣ Run Container Locally

```bash
docker run -dp 3000:3000 nodejs-app
```

---

### 4️⃣ Access Application

Open browser:

```
http://localhost:3000
```

---

## ☁️ AWS Deployment Steps

### 🔹 Step 1: Push Image to ECR

* Create ECR repository
* Authenticate Docker with AWS
* Tag and push image

---

### 🔹 Step 2: Create ECS Cluster

* Launch ECS cluster using Fargate
* Define task definition
* Configure container with port 3000

---

### 🔹 Step 3: Create ECS Service

* Attach Load Balancer
* Deploy container

---

### 🔹 Step 4: Setup CI/CD Pipeline

* Source: GitHub / CodeCommit
* Build: CodeBuild
* Deploy: ECS

---

## 📜 buildspec.yml Explanation

* **pre_build** → Login to ECR
* **build** → Build Docker image
* **post_build** → Push image to ECR & update ECS

---

## ⚠️ Challenges Faced

* Git authentication issue → solved using Personal Access Token
* Merge conflicts → resolved using proper Git workflow
* AWS permission errors → fixed using IAM roles

---

## 📚 Key Learnings

* CI/CD pipeline automation
* Docker containerization
* AWS ECS deployment
* Infrastructure as Code basics

---

## 🌐 Output

Application successfully deployed using AWS Load Balancer DNS.

---

## 🔗 GitHub Repository

https://github.com/pratikbadhe8483/cicd-aws-ecs-project

---

## 👨‍💻 Author

**Pratik Badhe**
DevOps & Cloud Enthusiast

---
