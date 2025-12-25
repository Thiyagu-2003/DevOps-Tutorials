---


<div align="center">

# 📦 Containers & Docker 🐳 — A Practical Introduction

### Learn Containers the Right Way (No Hand-Waving)

![Docker](https://img.shields.io/badge/Docker-Containerization-blue?logo=docker)
![Linux](https://img.shields.io/badge/Linux-Kernel-black?logo=linux)
![DevOps](https://img.shields.io/badge/DevOps-Foundations-orange)
![Beginner Friendly](https://img.shields.io/badge/Level-Beginner--Friendly-success)
<a href="https://github.com/Thiyagu-2003">
<img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-brightgreen?logo=github" />
</a>

</div>

---

## 📑 Table of Contents

- [📦 What is a Container?](#-what-is-a-container)
- [⚖️ Containers vs Virtual Machines](#️-containers-vs-virtual-machines)
- [⚡ Why Are Containers Lightweight?](#-why-are-containers-lightweight)
- [🐳 What is Docker?](#-what-is-docker)
- [🏗️ Docker Architecture](#️-docker-architecture)
- [🔄 Docker Lifecycle](#-docker-lifecycle)
- [📚 Docker Terminology](#-docker-terminology)
- [🛠️ Install Docker](#️-install-docker)
- [🚀 Containerize Your First App](#-containerize-your-first-app)
- [❤️ Footer](#️-footer)
- [👤 Author](#️-Author)

---

## 📦 What is a Container?

A **container** is a standard unit of software that packages:

- Application code  
- Required libraries  
- Minimal system dependencies  

So the application runs **consistently** across environments.

### In simple terms:

> **Container = Application + Dependencies + Minimal OS support**

Unlike virtual machines, containers **do not bundle an entire operating system**.

![Container Concept](https://user-images.githubusercontent.com/43399466/217262726-7cabcb5b-074d-45cc-950e-84f7119e7162.png)

---

## ⚖️ Containers vs Virtual Machines

| Feature | Containers | Virtual Machines |
|------|-----------|-----------------|
| OS | Share host kernel | Full OS per VM |
| Size | MBs | GBs |
| Startup Time | Seconds | Minutes |
| Resource Usage | Low | High |
| Portability | High | Medium |
| Isolation | Process-level | Hardware-level |

✔ Containers are **lighter & faster**  
✔ VMs provide **stronger isolation** but at a cost

---

## ⚡ Why Are Containers Lightweight?

Containers are lightweight because they:

- Share the **host OS kernel**
- Include **only what the app needs**
- Avoid bundling a full OS

### Real-world comparison

| Image Type | Approx Size |
|---------|-------------|
| Ubuntu Container Image | ~22 MB |
| Ubuntu VM Image | ~2.3 GB |

That’s nearly **100× smaller**.

![Ubuntu Image Size](https://user-images.githubusercontent.com/43399466/217493284-85411ae0-b283-4475-9729-6b082e35fc7d.png)

---

### 📁 Files Inside a Container Base Image

```

/bin    → Essential binaries
/sbin   → System binaries
/etc    → Configurations
/lib    → Shared libraries
/usr    → User utilities
/var    → Logs & runtime data
/root   → Root home directory

````

---

### 🧠 What Containers Borrow from the Host OS

| Host Resource | Purpose |
|-------------|---------|
| Kernel | System calls & scheduling |
| Networking | Connectivity |
| Namespaces | Isolation |
| cgroups | Resource limits |
| Filesystem | Mounts & volumes |

Containers are **isolated**, but **not blindfolded**.

---

## 🐳 What is Docker?

Docker is a **containerization platform** that allows you to:

- Build container images
- Run containers
- Push images to registries (Docker Hub, Quay, etc.)

### Key distinction

> **Containerization = Concept**  
> **Docker = Implementation**

---

## 🏗️ Docker Architecture

![Docker Architecture](https://user-images.githubusercontent.com/43399466/217507877-212d3a60-143a-4a1d-ab79-4bb615cb4622.png)

### Important truth

If the **Docker daemon stops**, Docker is effectively **dead**.

---

## 🔄 Docker Lifecycle

![Docker Lifecycle](https://user-images.githubusercontent.com/43399466/217511949-81f897b2-70ee-41d1-b229-38d0572c54c7.png)

### Core commands

```bash
docker build   # Build image
docker run     # Run container
docker push    # Push image to registry
````

These three commands are **non-negotiable knowledge**.

---

## 📚 Docker Terminology

| Term          | Meaning                                |
| ------------- | -------------------------------------- |
| Docker Daemon | Background service managing containers |
| Docker Client | CLI used to talk to daemon             |
| Dockerfile    | Instructions to build an image         |
| Image         | Read-only template                     |
| Container     | Running instance of an image           |
| Registry      | Stores images (Docker Hub, etc.)       |

---

## 🛠️ Install Docker

Official installation guide:

👉 [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)

### Example (Ubuntu / EC2)

```bash
sudo apt update
sudo apt install docker.io -y
```

---

### ▶️ Start Docker & Fix Permissions

```bash
sudo systemctl start docker
sudo systemctl status docker
```

Grant user access:

```bash
sudo usermod -aG docker ubuntu
```

⚠️ Logout & login again — **mandatory**

---

### ✅ Verify Installation

```bash
docker run hello-world
```

Expected output:

```
Hello from Docker!
This message shows that your installation appears to be working correctly.
```

If not — **fix permissions or daemon first**.

---

## 🚀 Containerize Your First App

You now understand:

* Containers
* Docker
* Images
* Lifecycle

👉 **Next step**: actually build something.

<div align="center">

<a href="https://docs.docker.com/get-started/">
  <img src="https://img.shields.io/badge/🔥%20Start%20Containerizing%20Your%20First%20App-Now-blue?style=for-the-badge&logo=docker" />
</a>

</div>

---

# 👤 **Author**

```
Name: Thiyagu S
Role: Cloud & DevOps Learner
Location: India 🇮🇳
GitHub: Thiyagu-2003
```

---

## ❤️ Footer

<p align="center">
  <strong>Built with ❤️ by Thiyagu S</strong><br>
  Learn • Build • Break • Fix • Repeat
</p>

---

