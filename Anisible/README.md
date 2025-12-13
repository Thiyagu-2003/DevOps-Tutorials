# 🔧 **Ansible Essentials – Complete Guide (Beginner → Advanced)**

---

## 📚 **Table of Contents**

1. [🔧 Configuration Management Overview](#configuration-management-overview)
2. [❓ Why Ansible?](#why-ansible)
3. [📄 Ansible Basics](#ansible-basics)
4. [⚖️ Puppet vs Ansible](#puppet-vs-ansible)
5. [🧠 Key Advantages of Ansible](#key-advantages-of-ansible)
6. [🧩 Ansible Modules](#ansible-modules)
7. [📌 Ad-hoc Commands vs Playbooks](#ad-hoc-commands-vs-playbooks)
8. [❌ Limitations of Ansible](#limitations-of-ansible)
9. [🎯 Interview Questions & Answers](#interview-questions--answers)
10. [🛠️ Hands-on: Ansible with Multiple EC2 Instances](#hands-on-ansible-with-multiple-ec2-instances)
11. [👤 Author](#author)

---

## 🔧 Configuration Management Overview

### Configuration Management Tools

* **Ansible** (most widely used)
* Puppet
* Chef

Configuration management ensures **consistent system state**, **repeatable deployments**, and **reduced manual errors** across servers.

---

## ❓ Why Ansible?

**Ansible uses a push-based architecture.**

* You define configurations on a **control node**
* Changes are **pushed to target nodes** over SSH / WinRM
* No agents. No polling. No background daemons

Think Git push, not cron-based pulling. This simplicity is the real reason Ansible wins.

---

## 📄 Ansible Basics

* Configuration logic is written in **Playbooks**
* Playbooks are written in **YAML**
* One-off tasks → **Ad-hoc commands**
* Complex workflows → **Playbooks**

**If you’re automating more than one step, ad-hoc commands are the wrong tool.**

---

## ⚖️ Puppet vs Ansible

| Feature        | Puppet         | Ansible                      |
| -------------- | -------------- | ---------------------------- |
| Mechanism      | Pull-based     | Push-based                   |
| Architecture   | Master / Agent | Agentless                    |
| Agent Required | Yes            | No                           |
| Node Setup     | Mandatory      | Not required                 |
| Authentication | Agent certs    | SSH (Linux), WinRM (Windows) |
| Automation     | Limited        | Fully automated              |
| OS Support     | Mostly Linux   | Linux + Windows              |
| Language       | Puppet DSL     | YAML                         |
| Adoption       | Declining      | Industry standard            |

---

## 🧠 Key Advantages of Ansible

* **Agentless** → zero footprint on target nodes
* **Human-readable YAML** → fewer mistakes
* Works with **Linux and Windows**
* Supports **Dynamic Inventory** (cloud-native)
* Custom modules via **Python**
* Thousands of reusable roles via **Ansible Galaxy**

---

## 🧩 Ansible Modules

* Modules are the actual execution units
* Written mostly in **Python**
* You *can* write your own modules (most people don’t need to)
* Community modules are distributed via **Ansible Galaxy**

If you’re rewriting shell scripts as modules too early, you’re overengineering.

---

## 📌 Ad-hoc Commands vs Playbooks

### Ad-hoc Commands

* One-time, quick actions
* No state tracking
* Not reusable

Example:

```bash
ansible all -m shell -a "uptime"
```

### Playbooks

* Multi-step automation
* Declarative
* Reusable and version-controlled

**Rule of thumb**

* 1 quick task → Ad-hoc
* Anything serious → Playbook

---

## ❌ Limitations of Ansible

* Windows support is weaker than Linux
* Debugging complex playbooks is painful
* Slower at massive scale compared to pull-based tools

If you’re managing tens of thousands of nodes, Ansible alone isn’t enough.

---

## 🎯 Interview Questions & Answers

1. **What language is Ansible written in?**
   Python

2. **What language are playbooks written in?**
   YAML

3. **What mechanism does Ansible use?**
   Push-based

4. **Does Ansible require agents?**
   No

5. **How does Ansible connect to Linux nodes?**
   SSH

6. **How does Ansible connect to Windows nodes?**
   WinRM

7. **Ad-hoc vs Playbooks?**
   Ad-hoc = quick tasks, Playbooks = structured automation

8. **Does Ansible support cloud providers?**
   Yes — AWS, Azure, GCP

---

## 🛠️ Hands-on: Ansible with Multiple EC2 Instances

> ⚠️ This section is **non-negotiable**. If this setup fails, Ansible will not work. Period.

### 🟢 Step 1: Install Ansible on Control Node

```bash
sudo apt update
sudo apt install ansible -y
ansible --version
```

---

### 🔐 Step 2: Configure Passwordless SSH (Critical Step)

#### On Control Node

```bash
ssh-keygen -t ed25519
```

This generates:

* **Public key** → `~/.ssh/id_ed25519.pub`
* **Private key** → `~/.ssh/id_ed25519`

**Never copy the private key. Ever.**

Copy the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

---

#### 🖥️ On Target EC2 Instance

```bash
nano ~/.ssh/authorized_keys
```

* **Do NOT delete existing keys**
* Paste the new key on a **new line**

Fix permissions:

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

---

#### **✅ Step 3: Test SSH**

```bash
ssh ubuntu@<TARGET_PUBLIC_IP>
```

If it asks for a password, the setup is wrong.

---

### 🗂️ Step 4: Create Inventory File

```bash
nano inventory
```

```ini
[servers]
<EC2_PUBLIC_IP>
```

---

### 🚀 Step 5: Run Ad-hoc Command

```bash
ansible -i inventory all -m shell -a "touch devopsclass"
```

If this works, your Ansible setup is correct.

---

## 👤 Author

```
Name   : Thiyagu S
Role   : Cloud & DevOps Learner
Country: India 🇮🇳
```

---

# ❤️ **Footer**

<p align="center">
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Learning • Building • Improving
</p>

---
