---

# ⭐ **JENKINS COMPLETE NOTES – BASIC → ADVANCED (CI/CD)**

<p align="center">
  <img src="https://img.shields.io/badge/Jenkins-CI/CD-red?logo=jenkins&logoColor=white" />
  <img src="https://img.shields.io/badge/Level-Beginner%20to%20Advanced-blue" />
  <img src="https://img.shields.io/badge/Format-README.md-success" />
  <a href="https://github.com/Thiyagu-2003">
    <img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-brightgreen?logo=github" />
  </a>
</p>

---

# 📑 **Table of Contents**

1. [📌 Introduction to Jenkins](#-1-introduction-to-jenkins)
2. [🔄 CI/CD Fundamentals](#-2-cicd-fundamentals)
3. [🏗 Jenkins Architecture](#-3-jenkins-architecture)
4. [⚙ Jenkins Installation & Setup](#-4-jenkins-installation--setup)
5. [🧱 Jenkins Jobs & Build Types](#-5-jenkins-jobs--build-types)
6. [🧪 Jenkins Pipelines (Declarative & Scripted)](#-6-jenkins-pipelines-declarative--scripted)
7. [🔐 Credentials & Security](#-7-credentials--security)
8. [🔗 Integrations (Docker, K8s, AWS)](#-8-integrations-docker-k8s-aws)
9. [🏗 CI/CD Architecture (Production Flow)](#-9-cicd-architecture-production-flow)
10. [🚀 Production Best Practices](#-10-production-best-practices)
11. [🎯 Common Interview Questions](#-11-common-interview-questions)
12. [👤 Author](#-author)
13. [❤️ Footer](#️-footer)

---

# **1. Introduction to Jenkins**

## 📌 What is Jenkins?

**Jenkins** is an open-source automation server used to implement Continuous Integration (CI) and Continuous Delivery/Deployment (CD).

It automates:

* Build
* Test
* Package
* Deploy

---

## 🎯 Why Jenkins?

| Problem Without CI/CD | Solution With Jenkins |
| --------------------- | --------------------- |
| Manual builds         | Automated builds      |
| Manual testing        | Automated testing     |
| Deployment errors     | Reliable deployment   |
| Slow release cycle    | Faster delivery       |

---

# **2. CI/CD Fundamentals**

## 🔄 Continuous Integration (CI)

* Developers push code frequently.
* Automatic build + test triggered.
* Bugs detected early.

## 🚀 Continuous Delivery (CD)

* Application automatically prepared for release.
* Can deploy to staging/production.

---

# **3. Jenkins Architecture**

| Component           | Role                            |
| ------------------- | ------------------------------- |
| Controller (Master) | Manages jobs & schedules builds |
| Agent (Slave)       | Executes build tasks            |
| Node                | Machine where job runs          |
| Executor            | Slot to run a build             |

### 🔹 Important Rule:

Never overload the controller with builds in production.

---

# **4. Jenkins Installation & Setup**

| Method          | Description           |
| --------------- | --------------------- |
| WAR File        | Run using Java        |
| Docker          | Containerized Jenkins |
| Package Manager | apt/yum installation  |

Runs on:

* Linux
* Windows
* macOS

Default Port: `8080`

---

# **5. Jenkins Jobs & Build Types**

## 🔹 Freestyle Project

Basic job configuration (UI based).

## 🔹 Pipeline Project

Pipeline defined using `Jenkinsfile`.

## 🔹 Multibranch Pipeline

Automatically builds all branches.

---

# **6. Jenkins Pipelines (Declarative & Scripted)**

## ✅ Declarative Pipeline (Recommended)

```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
    }
}
```

## ✅ Scripted Pipeline

```groovy
node {
    stage('Build') {
        echo 'Building...'
    }
}
```

| Type        | Use Case       |
| ----------- | -------------- |
| Declarative | Standard CI/CD |
| Scripted    | Advanced logic |

---

# **7. Credentials & Security**

## 🔐 Credentials Types

| Type              | Usage              |
| ----------------- | ------------------ |
| Username/Password | Git authentication |
| SSH Key           | Secure repo access |
| Secret Text       | API keys           |
| Secret File       | Certificates       |

Best Practices:

* Never hardcode secrets
* Use Jenkins Credentials Manager
* Enable role-based access

---

# **8. Integrations (Docker, K8s, AWS)**

Jenkins integrates with:

* **GitHub**
* **Docker**
* **Kubernetes**
* **Amazon Web Services**
* **Maven**

Example Flow:

1. Pull code from GitHub
2. Build with Maven
3. Create Docker image
4. Push to registry
5. Deploy to Kubernetes

---

# **9. CI/CD Architecture (Production Flow)**

```
Developer
   ↓
GitHub (Webhook)
   ↓
Jenkins Controller
   ↓
Build Agent
   ↓
Artifact Repository
   ↓
Docker Registry
   ↓
Kubernetes / EC2
```

## 🔹 Real Production Steps

| Step | Action          |
| ---- | --------------- |
| 1    | Code Push       |
| 2    | Webhook Trigger |
| 3    | Build           |
| 4    | Test            |
| 5    | Package         |
| 6    | Push Artifact   |
| 7    | Deploy          |
| 8    | Monitor         |

---

# **10. Production Best Practices**

| Practice                    | Why            |
| --------------------------- | -------------- |
| Use Distributed Agents      | Scalability    |
| Use HTTPS                   | Security       |
| Enable RBAC                 | Access control |
| Clean old builds            | Save disk      |
| Store artifacts externally  | Reliability    |
| Use Infrastructure as Code  | Automation     |
| Implement rollback strategy | Safety         |

---

# **11. Common Interview Questions**

### 1️⃣ What is Jenkins?

Automation server for CI/CD.

### 2️⃣ CI vs CD?

CI = build + test
CD = deploy

### 3️⃣ What is Jenkinsfile?

Pipeline definition stored in Git.

### 4️⃣ What is Blue-Green Deployment?

Two environments: one live, one idle. Switch traffic safely.

### 5️⃣ How do you secure Jenkins?

RBAC, HTTPS, credentials manager, plugin updates.

### 6️⃣ How do you scale Jenkins?

Use distributed agents or Kubernetes agents.

### 7️⃣ Poll SCM vs Webhook?

Webhook is event-driven and efficient.

---

# 👤 **Author**

```
Name: Thiyagu S
Role: AWS Cloud & DevOps Learner
Location: India 🇮🇳
GitHub: Thiyagu-2003
```

---

# ❤️ **Footer**

<p align="center">
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Automate • Build • Deploy • Improve
</p>

---
