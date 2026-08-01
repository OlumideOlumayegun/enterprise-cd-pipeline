# Enterprise Continuous Delivery Pipeline for Java Applications Using Jenkins, Docker, Amazon ECR, Amazon ECS, SonarQube, Nexus Repository, and GitHub

![project banner](./images/project-banner.png)

> An enterprise-grade Continuous Delivery (CD) pipeline that automates the build, quality assurance, containerisation, and deployment of a Java web application using Jenkins, Docker, Amazon ECR, Amazon ECS, SonarQube, Nexus Repository, and GitHub.

---

## 📖 Project Overview

This project demonstrates how to design and implement a production-style Continuous Delivery pipeline for a Java application. Beginning with a developer's code commit, the pipeline automatically compiles the application, executes quality checks, builds a Docker image, publishes it to Amazon Elastic Container Registry (ECR), and deploys it to an Amazon Elastic Container Service (ECS) staging environment.

Following successful validation and approval, the same immutable Docker image is promoted to a production ECS environment using a dedicated production deployment pipeline. This follows the DevOps best practice of **Build Once, Deploy Many**, ensuring consistency across environments.

The project simulates an enterprise CI/CD workflow commonly used by organisations deploying containerised Java applications on AWS.

---

## 🚀 Features

* Automated Continuous Integration and Continuous Delivery
* GitHub Webhook integration
* Maven build automation
* Unit testing
* Checkstyle code quality analysis
* SonarQube static code analysis
* SonarQube Quality Gate validation
* Nexus Repository artifact management
* Multi-stage Docker image builds
* Amazon Elastic Container Registry (ECR) integration
* Amazon Elastic Container Service (ECS) deployments
* AWS Fargate container hosting
* Separate Staging and Production pipelines
* Immutable Docker image versioning
* Automated rolling deployments
* Application Load Balancer integration
* Jenkins credential management
* AWS IAM integration

---

# 🏗 Solution Architecture

![project banner](./images/project-architecture.png)

---

# 🛠 Technologies Used

| Category            | Technologies                  |
| ------------------- | ----------------------------- |
| Source Control      | Git, GitHub                   |
| CI/CD               | Jenkins                       |
| Build Tool          | Maven                         |
| Code Quality        | SonarQube, Checkstyle         |
| Artifact Repository | Nexus Repository              |
| Containerisation    | Docker                        |
| Container Registry  | Amazon ECR                    |
| Container Platform  | Amazon ECS (Fargate)          |
| Cloud Platform      | AWS                           |
| Security            | AWS IAM                       |
| Deployment          | AWS CLI                       |
| Load Balancing      | AWS Application Load Balancer |

---

# 📁 Repository Structure

```text
.
├── Dockerfiles/
│   ├── app/
│   │   └── multi-stage/
│   ├── db/
│   └── web/
│
├── stage-pipeline/
│   └── Jenkinsfile
│
├── prod-pipeline/
│   └── Jenkinsfile
│
├── Setup-Guide.md
│
├── images/
│   ├── project-architecture.png
│   └── project-banner.png
│
├── settings.xm
├── src/
├── pom.xml
├── README.md
└── LICENSE
```

---

# ⚙ Prerequisites

Before starting this project, ensure the following are available:

* AWS Account
* GitHub Account
* Jenkins Server
* SonarQube Server
* Nexus Repository
* Docker Engine
* AWS CLI
* Java JDK 17 (or compatible)
* Maven
* Visual Studio Code
* Git

---

# 📋 Implementation Workflow

Detailed step-by-step implementation steps, configuration details, and workflow documentation are available in the [Setup Guide](./Setup-Guide.md).

## Phase 1 – Continuous Integration

* Configure Jenkins
* Configure SonarQube
* Configure Nexus Repository
* Configure GitHub Webhook
* Build Java application using Maven
* Execute Unit Tests
* Run Checkstyle
* Perform SonarQube Analysis
* Validate Quality Gate
* Publish WAR artifact

---

## Phase 2 – Docker Image Build

* Create multi-stage Dockerfile
* Build application container
* Tag Docker image
* Authenticate with Amazon ECR
* Push Docker image

---

## Phase 3 – Staging Deployment

* Create ECS Cluster
* Create Task Definition
* Configure ECS Service
* Configure Application Load Balancer
* Deploy latest Docker image
* Execute validation testing

---

## Phase 4 – Production Deployment

* Create Production ECS Cluster
* Create Production Service
* Create Production Jenkins Pipeline
* Promote validated Docker image
* Deploy to Production

---

# 🔄 Continuous Delivery Workflow

```text
Developer Commit
        │
        ▼
GitHub Repository
        │
        ▼
GitHub Webhook
        │
        ▼
Jenkins CI/CD Pipeline
        │
        ├── Checkout Source
        ├── Maven Build
        ├── Unit Tests
        ├── Checkstyle
        ├── SonarQube Scan
        ├── Quality Gate
        ├── Build Docker Image
        ├── Push Docker Image
        │      to Amazon ECR
        └── Deploy to ECS Staging
                    │
                    ▼
            Functional Testing
                    │
            Manual Approval
                    │
                    ▼
           Merge to Production
                    │
                    ▼
       Jenkins Production Pipeline
                    │
                    ▼
      Deploy Existing Docker Image
                    │
                    ▼
         Amazon ECS Production
```

---

# 🚀 Getting Started

## Clone the Repository

```bash
git clone https://github.com/<username>/<repository>.git

cd <repository>
```

---

## Create a Development Branch

```bash
git checkout -b jenkins-ci-cd
```

---

## Configure Jenkins

Install the required plugins:

* Docker Pipeline
* CloudBees Docker Build and Publish
* Amazon ECR
* Pipeline: AWS Steps

Configure:

* GitHub credentials
* AWS credentials
* Docker
* AWS CLI

---

## Configure AWS

Create:

* Amazon ECR Repository
* IAM User
* ECS Staging Cluster
* ECS Production Cluster
* ECS Services
* Application Load Balancers

---

## Configure GitHub

Configure a webhook pointing to Jenkins:

```
http://<jenkins-public-ip>:8080/github-webhook/
```

---

## Run the Pipeline

Push any code change to GitHub.

The pipeline automatically:

* Builds the application
* Executes quality checks
* Builds Docker images
* Pushes images to Amazon ECR
* Deploys to Amazon ECS

---

# 📸 Expected Pipeline

```text
✔ Checkout Source

✔ Maven Build

✔ Unit Tests

✔ Checkstyle

✔ SonarQube Analysis

✔ Quality Gate

✔ Docker Build

✔ Push to Amazon ECR

✔ Deploy to ECS Staging

✔ Production Promotion

✔ Deploy to Production
```

---

# 📈 Skills Demonstrated

This project demonstrates practical experience with:

* DevOps Engineering
* Continuous Integration
* Continuous Delivery
* Jenkins Pipelines
* Pipeline as Code
* GitHub Webhooks
* Maven
* SonarQube
* Nexus Repository
* Docker
* Multi-stage Docker Builds
* AWS IAM
* Amazon ECR
* Amazon ECS
* AWS Fargate
* Application Load Balancers
* CI/CD Best Practices
* Production Release Management

---

# 🎯 Key Learning Outcomes

* Build enterprise-grade CI/CD pipelines
* Integrate multiple DevOps tools
* Containerise Java applications
* Automate AWS deployments
* Implement immutable deployments
* Separate staging and production environments
* Follow Build Once, Deploy Many principles
* Apply enterprise DevOps deployment strategies

---

# 📚 Related Documentation

* **Implementation Guide** – Complete step-by-step project implementation.
* **Architecture Diagram** – End-to-end deployment architecture.
* **Jenkinsfiles** – Pipeline as Code definitions.
* **Dockerfiles** – Multi-stage Docker build configuration.

---

# 🔮 Future Improvements

Potential enhancements include:

* Infrastructure as Code using Terraform
* Kubernetes deployment using Amazon EKS
* Blue/Green deployments
* Canary deployments
* GitOps with Argo CD
* Helm charts
* Trivy container image scanning
* OWASP Dependency-Check integration
* Prometheus monitoring
* Grafana dashboards
* Amazon CloudWatch dashboards
* Slack and Microsoft Teams notifications

---

# 👨‍💻 Author

**Olumide Olumayegun**

**Process Engineer | DevOps Engineer | Data Scientist**

**Bridging DevOps, Data Science, and AI – From Deployment Pipelines to Deep Insights**

---

