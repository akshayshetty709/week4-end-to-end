# 🚀 End-to-End DevOps CI/CD Pipeline

### GitHub → GitHub Actions → Docker → Amazon ECR → Amazon EKS → Monitoring → Email Notification

![CI/CD](https://img.shields.io/badge/CI-CD-GitHub%20Actions-blue)
![Docker](https://img.shields.io/badge/Container-Docker-blue)
![Kubernetes](https://img.shields.io/badge/Orchestration-Kubernetes-blue)
![AWS](https://img.shields.io/badge/Cloud-AWS-orange)
![Monitoring](https://img.shields.io/badge/Monitoring-Prometheus%20%7C%20Grafana-green)

---

# 📌 Project Overview

This project demonstrates a **complete end-to-end DevOps CI/CD pipeline** that automates the build, containerization, and deployment of an application on Kubernetes using AWS services.

Whenever a developer pushes code to the GitHub repository, the pipeline automatically:

1. Builds a Docker image
2. Pushes the image to Amazon ECR
3. Deploys the application to Amazon EKS
4. Sends email notifications for pipeline status
5. Monitors the application using monitoring tools

This project showcases real-world **DevOps automation and cloud deployment practices**.

---

# 🏗 Architecture Diagram

```
Developer
   │
   │ Push Code
   ▼
GitHub Repository
   │
   ▼
GitHub Actions CI/CD Pipeline
   │
   ├── Build Docker Image
   ├── Push Image to Amazon ECR
   ├── Deploy to Amazon EKS
   │
   ▼
Amazon EKS Cluster
   │
   ├── Kubernetes Deployment
   ├── Kubernetes Service (LoadBalancer)
   │
   ▼
Running Application
   │
   ├── Monitoring (Prometheus + Grafana / CloudWatch)
   └── Email Notification
```

---

# 🛠 Technologies Used

| Tool           | Purpose                 |
| -------------- | ----------------------- |
| GitHub         | Source code management  |
| GitHub Actions | CI/CD automation        |
| Docker         | Containerization        |
| Amazon ECR     | Container registry      |
| Amazon EKS     | Kubernetes cluster      |
| Kubernetes     | Container orchestration |
| kubectl        | Kubernetes CLI          |
| Prometheus     | Monitoring              |
| Grafana        | Visualization           |
| AWS SNS / SMTP | Email notifications     |

---

# 📂 Project Structure

```
devops-ci-cd-project
│
├── app
│   ├── app.js
│   └── package.json
│
├── Dockerfile
│
├── k8s
│   ├── deployment.yaml
│   └── service.yaml
│
└── .github
    └── workflows
        └── deploy.yml
```

---

# ⚙ CI/CD Pipeline Workflow

The automated pipeline performs the following stages:

### 1️⃣ Code Push

A developer pushes code to the **main branch** of the GitHub repository.

### 2️⃣ GitHub Actions Trigger

GitHub Actions automatically triggers the CI/CD workflow.

### 3️⃣ Docker Image Build

The pipeline builds a Docker image of the application.

```
docker build -t node-app .
```

### 4️⃣ Push Image to Amazon ECR

The built Docker image is pushed to the AWS ECR repository.

```
docker tag node-app:latest <ECR_URL>/node-app:latest
docker push <ECR_URL>/node-app:latest
```

### 5️⃣ Deploy to Amazon EKS

Kubernetes manifests are applied to deploy the application.

```
kubectl apply -f k8s/
```

### 6️⃣ Application Deployment

The application runs inside Kubernetes pods and is exposed via a **LoadBalancer service**.

---

# 📊 Monitoring

Application and cluster metrics are monitored using:

* Prometheus
* Grafana
* AWS CloudWatch (optional)

Metrics tracked include:

* Pod health
* CPU usage
* Memory utilization
* Node status

---

# 📧 Email Notification

Email alerts are sent for:

* Successful deployments
* Pipeline failures
* System alerts

Notifications can be configured using:

* GitHub Actions mail integration
* AWS SNS

---

# 🔍 Useful Commands

Check pods

```
kubectl get pods
```

Check services

```
kubectl get svc
```

Check deployments

```
kubectl get deployments
```

---

# 🎯 Learning Outcomes

This project demonstrates practical experience in:

* CI/CD pipeline implementation
* Containerization using Docker
* Kubernetes application deployment
* AWS cloud integration
* Infrastructure monitoring
* DevOps automation practices

---

# 🚀 Future Enhancements

Possible improvements for this project include:

* Infrastructure provisioning using **Terraform**
* GitOps deployment using **ArgoCD**
* Implementing **Blue-Green Deployment**
* Adding **automated testing stages**
* Integrating **Slack alerts**

---

# 👨‍💻 Author

**Akshay Shetty**

DevOps Engineer
AWS | Docker | Kubernetes | CI/CD | Cloud Automation
