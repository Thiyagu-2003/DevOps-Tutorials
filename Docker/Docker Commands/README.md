---


# 🐳  Docker Commands – Clean & Practical Guide

<p align="center">
  <img src="https://img.shields.io/badge/Docker-Commands-blue?logo=docker" />
  <img src="https://img.shields.io/badge/DevOps-Foundations-orange" />
  <img src="https://img.shields.io/badge/Containers-Management-success" />
  <a href="https://github.com/Thiyagu-2003">
    <img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-brightgreen?logo=github" />
  </a>
</p>

---

## 📚 Table of Contents

- 🔹 [📌 What are Docker Commands?](#-what-are-docker-commands)
- 🔹 [🧩 Why Docker Commands Matter](#-why-docker-commands-matter)
- 🔹 [🐳 Image Management Commands](#-image-management-commands)
- 🔹 [📦 Container Lifecycle Commands](#-container-lifecycle-commands)
- 🔹 [🌐 Networking Commands](#-networking-commands)
- 🔹 [💾 Volume Commands](#-volume-commands)
- 🔹 [📊 Monitoring & Debugging Commands](#-monitoring--debugging-commands)
- 🔹 [🧹 Cleanup Commands](#-cleanup-commands)
- 🔹 [⚠️ Common Mistakes](#️-common-mistakes-you-were-making-these)
- 🔹 [🧠 Key Takeaways](#-key-takeaways)
- 🔹 [👤 Author](#-author)
- 🔹 [❤️ Footer](#️-footer)

---

## 📌 What are Docker Commands?

Docker commands are **CLI instructions** used to:
- Build images
- Run containers
- Manage networks & volumes
- Monitor and debug running applications

📌 **Docker CLI is the control plane of containerized systems**

---

## 🧩 Why Docker Commands Matter

Without understanding Docker commands:
- You cannot debug containers
- You cannot manage resources
- You cannot deploy reliably

📌 **Tools don’t replace fundamentals**

---

## 🐳 Image Management Commands

### 🔹 Pull an image
```bash
docker pull nginx
````

📌 Downloads an image from Docker Hub

---

### 🔹 List images

```bash
docker images
```

📌 Shows locally available images

---

### 🔹 Build an image

```bash
docker build -t my-app .
```

📌 Creates an image from a Dockerfile

---

### 🔹 Remove an image

```bash
docker rmi nginx
```

📌 Deletes unused images

---

## 📦 Container Lifecycle Commands

### 🔹 Run a container

```bash
docker run -d -p 80:80 --name web nginx
```

📌 Creates and starts a container

---

### 🔹 List running containers

```bash
docker ps
```

### 🔹 List all containers

```bash
docker ps -a
```

---

### 🔹 Stop a container

```bash
docker stop web
```

---

### 🔹 Start a container

```bash
docker start web
```

---

### 🔹 Remove a container

```bash
docker rm web
```

---

## 🌐 Networking Commands

### 🔹 List networks

```bash
docker network ls
```

---

### 🔹 Create a network

```bash
docker network create app-network
```

---

### 🔹 Inspect a network

```bash
docker network inspect app-network
```

---

### 🔹 Connect container to network

```bash
docker network connect app-network web
```

---

## 💾 Volume Commands

### 🔹 List volumes

```bash
docker volume ls
```

---

### 🔹 Create a volume

```bash
docker volume create app-data
```

---

### 🔹 Inspect a volume

```bash
docker volume inspect app-data
```

---

### 🔹 Run container with volume

```bash
docker run -d -v app-data:/data nginx
```

---

## 📊 Monitoring & Debugging Commands

### 🔹 View logs

```bash
docker logs web
```

---

### 🔹 Follow logs

```bash
docker logs -f web
```

---

### 🔹 Execute command inside container

```bash
docker exec -it web bash
```

---

### 🔹 View resource usage

```bash
docker stats
```

---

## 🧹 Cleanup Commands

### 🔹 Remove stopped containers

```bash
docker container prune
```

---

### 🔹 Remove unused images

```bash
docker image prune
```

---

### 🔹 Remove unused volumes

```bash
docker volume prune
```

⚠️ **Permanent deletion – use carefully**

---

## ⚠️ Common Mistakes (You Were Making These)

❌ Running everything with `latest` tag
✔ Use versioned images

❌ Not naming containers
✔ Makes debugging painful

❌ No cleanup strategy
✔ Leads to disk exhaustion

❌ Blindly pruning in production
✔ Data loss risk

---

## 🧠 Key Takeaways

* Docker CLI is **non-optional knowledge**
* Group commands by **intent**, not memory
* Learn what a command **does**, not just syntax
* Commands + architecture = real skill

---

## 👤 Author

```
Name    : Thiyagu S
Role    : Cloud & DevOps Learner
Location: India 🇮🇳
GitHub  : Thiyagu-2003
```

---

## ❤️ Footer

<p align="center">
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Learning • Building • Improving
</p>


---
