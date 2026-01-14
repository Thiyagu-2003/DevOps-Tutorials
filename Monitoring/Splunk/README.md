---

# 📘 **DevOps Essentials – Complete Documentation Index**

<p align="center">
<img src="https://img.shields.io/badge/DevOps-Essentials-orange?logo=dev.to&logoColor=white" />
<img src="https://img.shields.io/badge/Docs-8%20Services-blue" />
<a href="https://github.com/Thiyagu-2003">
<img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-brightgreen?logo=github" />
</a>
</p>

---

# 📊 SPLUNK – Log Monitoring & Analysis
> **Monitoring Tool | Log Analytics Platform**

---

## 📑 Table of Contents
1. [What is Splunk?](#what-is-splunk)
2. [Types of Monitoring](#types-of-monitoring)
3. [What is a Log?](#what-is-a-log)
4. [Types of Logs](#types-of-logs)
5. [Log Levels](#log-levels)
6. [Log Retention](#log-retention)
7. [Log Paths](#log-paths)
8. [Splunk Editions & Licensing](#splunk-editions--licensing)
9. [Splunk Architecture](#splunk-architecture)
10. [Splunk Components](#splunk-components)
11. [Ports Used by Splunk](#ports-used-by-splunk)
12. [Installation Steps](#installation-steps)
13. [Configuration: Master & Slave](#configuration-master--slave)
14. [Verification](#verification)

---

## 🔍 What is Splunk?
Splunk is a **log monitoring, searching, and analytics platform** used to analyze **machine-generated data** in real time.

➡️ **Primary Use Case:**  
**Log Monitoring** (not UI monitoring, not server management)

---

## 🧭 Types of Monitoring
Splunk can be used for:

- **Application Monitoring**
- **Server Monitoring**
- **Network Monitoring**
- **Log Monitoring** ✅ *(Primary use case)*

---

## 📝 What is a Log?
A **log** is an **event or entry** that records system or application activity.

Example:
- User login / logout
- Error messages
- Server commands
- Network events

Splunk works using:
- **Keyword-based search**
- **Query-based search (SPL – Search Processing Language)**

---

## 📂 Types of Logs
### 1. Application Logs
- Login success/failure
- Password attempts
- Business events

**Example:**
```

application.log

```

### 2. Server Logs
- EC2 login
- Command execution
- System activity

**Example:**
```

/var/log/syslog

````

### 3. Network Logs
- Firewall
- Load balancer
- Network traffic

---

## 🚦 Log Levels
Standard log severity levels:

- `INFO`   → Normal operation  
- `DEBUG`  → Troubleshooting  
- `ERROR`  → Failures & exceptions  

---

## 🕒 Log Retention
Logs are **not stored forever**.

Typical retention:
- **30 days**
- **90 days**

Old logs are usually:
- **Compressed**
- **Zipped**
- **Archived**

---

## 📁 Log Paths

### Linux
```bash
/opt/<application>/log/application.log
/opt/<application>/log/application_13062021.log
````

### Windows

```text
C:\Application\Logs\
```

---

## 💰 Splunk Editions & Licensing

| Edition                          | Limits             |
| -------------------------------- | ------------------ |
| **Splunk Enterprise (Trial)**    | 60 days            |
| **Daily Ingestion (Trial)**      | 500 MB/day         |
| **Splunk Enterprise (Licensed)** | 100 GB/day or more |

⚠️ **Splunk is NOT free in production**

---

## 🏗 Splunk Architecture

Splunk follows a **Master–Slave (Centralized)** architecture.

* **Master** → Splunk Enterprise
* **Slave** → Splunk Forwarder

---

## 🧩 Splunk Components

### 1️⃣ Search Head

* UI access
* Where queries are written
* Dashboards & reports

### 2️⃣ Indexer

* Stores indexed log data
* Fast searching

### 3️⃣ Forwarder

* Installed on servers (EC2)
* Sends logs to master

---

## 🔌 Ports Used by Splunk

| Purpose            | Port     |
| ------------------ | -------- |
| Forwarder → Master | **9997** |
| Web UI             | 8000     |

---

## 🖥 Installation Steps (Linux)

### Step 1: Extract Splunk

```bash
tar -xvzf splunk-<version>.tgz
```

### Step 2: Navigate

```bash
cd splunk
cd bin
```

### Step 3: Start Splunk

```bash
./splunk start --accept-license
```

OR

```bash
/opt/splunk/bin/splunk start
```

---

## ⚙️ Configuration: Master & Slave

### 🔹 Master Configuration

Enable listener on **9997**

```bash
/opt/splunk/bin
./splunk enable listen 9997
```

> Master should:

* Run **only Splunk**
* Not host other applications
* Can monitor **up to ~1000 servers**

---

### 🔹 Slave Configuration

Set master destination:

```bash
/opt/splunkforwarder/bin
./splunk add forward-server <MASTER_IP>:9997
```

Add log to monitor:

```bash
./splunk add monitor /var/log/syslog -index main
```

---

## ✅ Verification

Check Splunk process:

```bash
ps -ef | grep splunk
```

Same method as Jenkins verification.

---

## 📌 Key Takeaways

* Splunk = **Log Monitoring**
* Forwarders send → Indexer stores → Search Head queries
* Port **9997** is critical
* Logs = **Business impact visibility**

---

# 👤 **Author**

```
Name: Thiyagu S
Role: Cloud & DevOps Learner
Location: India 🇮🇳
GitHub: Thiyagu-2003
```

---

# ❤️ **Footer**

<p align="center">
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Learning • Building • Improving
</p>

---

