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
- [👤 Author](#-author)
- [❤️ Footer](#️-footer)

---

## 📦 What is a Container?

A **container** is a standard unit of software that packages:

- Application code  
- Required libraries  
- Minimal system dependencies  

So the application runs **consistently** across environments.

### In simple terms

> **Container = Application + Dependencies + Minimal OS support**

Unlike virtual machines, containers **do not bundle an entire operating system**.

![Container Concept](https://user-images.githubusercontent.com/43399466/217262726-7cabcb5b-074d-45cc-950e-84f7119e7162.png)

---

## ⚖️ Containers vs Virtual Machines

| Feature | Containers | Virtual Machines |
|------|-----------|-----------------|
| Operating System | Shared host kernel | Full OS per VM |
| Image Size | MBs | GBs |
| Startup Time | Seconds | Minutes |
| Resource Usage | Low | High |
| Portability | High | Medium |
| Isolation | Process-level | Hardware-level |

✔ Containers are **lighter & faster**  
✔ VMs offer **stronger isolation**, but with higher overhead

---

## ⚡ Why Are Containers Lightweight?

Containers are lightweight because they:

- Share the **host OS kernel**
- Include **only what the application needs**
- Avoid bundling a full operating system

### Real-world comparison

| Image Type | Approximate Size |
|----------|------------------|
| Ubuntu Container Image | ~22 MB |
| Ubuntu VM Image | ~2.3 GB |

That’s almost **100× smaller**.

![Ubuntu Image Size](https://user-images.githubusercontent.com/43399466/217493284-85411ae0-b283-4475-9729-6b082e35fc7d.png)

---

### 📁 Files Inside a Container Base Image

```

/bin    → Essential binaries
/sbin   → System binaries
/etc    → Configuration files
/lib    → Shared libraries
/usr    → User utilities
/var    → Logs & runtime data
/root   → Root user home directory

````

---

### 🧠 What Containers Borrow from the Host OS

| Host Resource | Purpose |
|--------------|---------|
| Kernel | System calls & scheduling |
| Networking | Network connectivity |
| Namespaces | Process & resource isolation |
| cgroups | CPU & memory limits |
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

### Hard truth

If the **Docker daemon stops**, Docker becomes useless.  
The daemon **is the brain** of Docker.

---

## 🔄 Docker Lifecycle

![Docker Lifecycle](https://user-images.githubusercontent.com/43399466/217511949-81f897b2-70ee-41d1-b229-38d0572c54c7.png)

### Core commands you must know

```bash
docker build   # Build an image
docker run     # Run a container
docker push    # Push image to registry
````

If you don’t understand these three, you don’t understand Docker.

---

## 📚 Docker Terminology

| Term          | Meaning                                    |
| ------------- | ------------------------------------------ |
| Docker Daemon | Background service managing Docker objects |
| Docker Client | CLI used to interact with Docker           |
| Dockerfile    | Instructions to build an image             |
| Image         | Read-only template                         |
| Container     | Running instance of an image               |
| Registry      | Stores images (Docker Hub, etc.)           |

---

## 🛠️ Install Docker

Official installation guide (always trust this first):

👉 [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)

### Example: Ubuntu / AWS EC2

```bash
sudo apt update
sudo apt install docker.io -y
```

---

### ▶️ Start Docker & Fix Permissions

Start the daemon:

```bash
sudo systemctl start docker
sudo systemctl status docker
```

Grant user permission:

```bash
sudo usermod -aG docker ubuntu
```

⚠️ **Logout and login again** — not optional.

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

If it fails, **fix the daemon or permissions first**.
Docker is not broken — your setup is.

---

## 🚀 Containerize Your First App

At this point, you understand:

* Containers
* Docker
* Images
* Lifecycle

👉 Now stop reading and **build something**.

---

## 🐳 Docker – Containerize Your First App Tutorial

<p align="center">
  <a href="https://github.com/Thiyagu-2003/DevOps-Tutorials/blob/main/Docker/MY-Pothfolio-Docker-image/README.md">
    <img src="https://img.shields.io/badge/Open-Docker%20Tutorial-2563eb?style=for-the-badge&logo=docker" alt="Open Docker Tutorial"/>
  </a>
</p>

**This tutorial covers:**

- ✅ Building Docker images  
- ✅ Running containers  
- ✅ Pushing images to Docker Hub  

---


## 📦 Docker Volumes – Persistent Storage

<p align="center">
  <a href="https://github.com/Thiyagu-2003/DevOps-Tutorials/blob/main/Docker/Docker-Volumes/README.md">
    <img src="https://img.shields.io/badge/Open-Docker%20Volumes-2563eb?style=for-the-badge&logo=docker" alt="Open Docker Volumes"/>
  </a>
</p>

**This tutorial covers:**

* ✅ What Docker volumes are
* ✅ Creating and listing volumes
* ✅ Mounting volumes to containers
* ✅ Persisting data after container restarts
* ✅ Volumes vs Bind mounts

📌 **Recommended for production workloads**

---

## 🌐 Docker Networking – Container Communication

<p align="center">
  <a href="https://github.com/Thiyagu-2003/DevOps-Tutorials/blob/main/Docker/Docker-Networking/README.md">
    <img src="https://img.shields.io/badge/Open-Docker%20Networking-2563eb?style=for-the-badge&logo=docker" alt="Open Docker Networking"/>
  </a>
</p>

**This tutorial covers:**

* ✅ Default Docker networks
* ✅ Bridge, host, and none networks
* ✅ Creating custom networks
* ✅ Container-to-container communication
* ✅ Network inspection and troubleshooting

📌 **Essential for multi-container apps**

---

## ⚙️ Docker Basic Commands – Daily Essentials

<p align="center">
  <a href="https://github.com/Thiyagu-2003/DevOps-Tutorials/blob/main/Docker/Docker-Basic-Commands/README.md">
    <img src="https://img.shields.io/badge/Open-Docker%20Commands-2563eb?style=for-the-badge&logo=docker" alt="Open Docker Commands"/>
  </a>
</p>

**This tutorial covers:**

* ✅ Image management commands
* ✅ Container lifecycle commands
* ✅ Logs, exec, and inspect
* ✅ Cleanup (prune, remove)
* ✅ Useful real-world command examples

📌 **Must-know commands for every DevOps engineer**

---


## 👤 Author

```
Name     : Thiyagu S
Role     : Cloud & DevOps Learner
Location : India 🇮🇳
GitHub   : Thiyagu-2003
```

---

## ❤️ Footer

<p align="center">
  <strong>Built with ❤️ by Thiyagu S</strong><br>
  Learn • Build • Break • Fix • Repeat
</p>

---







