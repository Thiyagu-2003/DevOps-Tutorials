---


<div align="center">

# 🐳 Dockerizing a Vite + React + Tailwind Application

### Production-Ready Containerization Using Docker & Nginx

![Docker](https://img.shields.io/badge/Docker-Containerization-blue?logo=docker)
![React](https://img.shields.io/badge/React-Frontend-61DAFB?logo=react)
![Vite](https://img.shields.io/badge/Vite-Build_Tool-646CFF?logo=vite)
![Tailwind](https://img.shields.io/badge/TailwindCSS-Utility--First-38B2AC?logo=tailwindcss)
![Nginx](https://img.shields.io/badge/Nginx-Web_Server-green?logo=nginx)

<a href="https://github.com/Thiyagu-2003">
  <img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-brightgreen?logo=github" />
</a>

<p align="center">
A no-nonsense guide to Dockerizing a modern frontend stack  
<strong>(Vite + React + Tailwind)</strong> the <strong>correct production way</strong>.
</p>

</div>

---

## 📌 Overview

This guide explains how to **containerize a Vite + React + Tailwind application using Docker** the **correct, production-ready way**.

We use a **multi-stage Docker build** to:

- Build the app using Node.js
- Serve the final static files using Nginx
- Produce a **small, fast, secure Docker image**

This is the approach you **should use in real projects and interviews**.

---

## 📑 Table of Contents

- [✅ Production Approach (Correct Way)](#-production-approach-correct-way)
- [⚠️ Required `.dockerignore`](#️-required-dockerignore)
- [🧱 Production Dockerfile](#-production-dockerfile)
- [🧠 Big Picture: How This Dockerfile Works](#-big-picture-how-this-dockerfile-works)
- [🧱 Stage 1: Build the App (Node.js)](#-stage-1-build-the-app-nodejs)
- [🚀 Stage 2: Serve the App (Nginx)](#-stage-2-serve-the-app-nginx)
- [✅ Final Result](#-final-result)
- [🧠 Brutal Checkpoint](#-brutal-checkpoint)
- [🚀 Dockerized Portfolio – Production Guide](#-dockerized-portfolio--production-guide)
- [🛠️ Build & Run (Production)](#️-build--run-production)
- [📦 Push Image to Docker Hub](#-push-image-to-docker-hub)
- [👤 Author](#-author)
- [❤️ Footer](#️-footer)

---

## ✅ Production Approach (Correct Way)

> **PRODUCTION / CORRECT WAY – This is what you SHOULD use**

✔ Multi-stage Docker build  
✔ Node.js only for building  
✔ Nginx for serving static files  
✔ Small, secure, production-ready image  

---

## ⚠️ Required `.dockerignore`

Create a file named **`.dockerignore`** in your project root:

```txt
node_modules
dist
.git
.gitignore
Dockerfile
README.md
````

### ❌ If you skip this

* Slow builds
* Huge images
* Amateur mistake

There is **zero excuse** for not using `.dockerignore`.

---

## 🧱 Production Dockerfile

> Docker reads **top → bottom**, exactly in this order.
> Replace your `Dockerfile` **entirely** with the following:

```dockerfile
# Stage 1: Build the app
FROM node:20-alpine AS builder

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build


# Stage 2: Serve with Nginx
FROM nginx:alpine

COPY --from=builder /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

---

## 🧠 Big Picture: How This Dockerfile Works

This Dockerfile has **two stages**:

### 🧱 Stage 1 — Builder

* Uses **Node.js**
* Builds the **React + Vite + Tailwind** app
* Produces static files in `dist/`

### 🚀 Stage 2 — Runtime

* Uses **Nginx**
* Serves static files
* Contains **NO Node.js**, **NO npm**, **NO source code**

🎯 Purpose:

* Smaller image
* Better security
* Production-ready deployment

If someone can’t explain this, they don’t actually understand Docker.

---

## 🧱 Stage 1: Build the App (Node.js)

```dockerfile
FROM node:20-alpine AS builder
```

* Lightweight Alpine Linux
* Node.js 20
* Named stage for later reference

```dockerfile
WORKDIR /app
```

Equivalent to:

```bash
cd /app
```

Skipping this causes chaos. Period.

```dockerfile
COPY package*.json ./
RUN npm install
```

* Enables Docker layer caching
* Faster rebuilds
* Dependency-only layer

```dockerfile
COPY . .
RUN npm run build
```

🚨 This produces:

```
/app/dist
```

Pure static files.
Node.js is now useless — which is the point.

---

## 🚀 Stage 2: Serve the App (Nginx)

```dockerfile
FROM nginx:alpine
```

Fresh container.
No Node.
No npm.
No source code.

```dockerfile
COPY --from=builder /app/dist /usr/share/nginx/html
```

This is the **entire reason** multi-stage builds exist.

```dockerfile
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

* Documents port usage
* Keeps Nginx running in foreground

Remove this → container exits instantly.

---

## ✅ Final Result

### Included

* Nginx ✅
* Static files ✅

### Excluded

* Node.js ❌
* npm ❌
* Source code ❌
* `node_modules` ❌

### Outcome

✔ Smaller
✔ Faster
✔ More secure
✔ Interview-proof

---

## 🧠 Brutal Checkpoint

**Question**

> Why don’t we use Node.js in the final image?

**Correct Answer**

> Because Vite builds static files, and Nginx can serve them without Node, reducing image size and attack surface.

If you hesitate — you don’t understand this yet.

---

# 🚀 Dockerized Portfolio – Production Guide

This section covers **building**, **running**, and **pushing** the production image.

---

## 🛠️ Build & Run (Production)

### Build Image

```bash
docker build -t thiyagu-portfolio-prod .
```

### Run Container

```bash
docker run -d -p 8080:80 thiyagu-portfolio-prod
```

Open:

```
http://localhost:8080
```

---

## 🔍 Sanity Checks

```bash
docker ps
docker images
```

If the image isn’t listed — stop and fix it.

---

## 📦 Push Image to Docker Hub

### Required Naming Format

```
<username>/<repository>:<tag>
```

### Tag Image

```bash
docker tag thiyagu-portfolio-prod:latest thiyagu2003/thiyagu-portfolio:latest
```

### Login

```bash
docker login
```

### Push

```bash
docker push thiyagu2003/thiyagu-portfolio:latest
```

Expected size: **~25–30 MB**

If it’s bigger — you screwed up the build.

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
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Learning • Building • Improving
</p>

---
