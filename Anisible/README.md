---

# 🔧 **Ansible Essentials – Complete Guide (Beginner → Advanced)**

<p align="center">
  <img src="https://img.shields.io/badge/Ansible-Commands-blue?logo=ansible" />
  <img src="https://img.shields.io/badge/SysAdmin-Essentials-green" />
  <img src="https://img.shields.io/badge/Level-Basic%20to%20Advanced-orange" />
  <a href="https://github.com/Thiyagu-2003">
    <img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-green?logo=github" />
  </a>
</p>

---

## 📚 Table of Contents

1. [Configuration Management Overview](#-configuration-management-overview)
2. [Why Ansible?](#-why-ansible)
3. [Ansible Basics](#-ansible-basics)
4. [Puppet vs Ansible](#-puppet-vs-ansible)
5. [Key Advantages](#-key-advantages-of-ansible)
6. [Ansible Modules](#-ansible-modules)
7. [Ad-hoc Commands vs Playbooks](#-ad-hoc-commands-vs-playbooks)
8. [Limitations of Ansible](#-limitations-of-ansible)
9. [Interview Questions](#-interview-questions--answers)
10. [Hands-on: Ansible with EC2](#-hands-on-ansible-with-multiple-ec2-instances)
11. [Author & Footer](#-author)

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
* No agents. No polling. No background daemons.

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
   → Python

2. **Have you created a custom Ansible module?**
   → Yes, using Python (or explain conceptually if not)

3. **What platforms does Ansible support?**
   → Linux (SSH) and Windows (WinRM)

4. **Why choose Ansible over other configuration tools?**
   → Agentless, push-based, simple YAML, fast setup

5. **What mechanism does Ansible use?**
   → Push mechanism

6. **What language is used to write playbooks?**
   → YAML

7. **Does Ansible support cloud providers?**
   → Yes, all major cloud providers (AWS, Azure, GCP)
   Requirement: Public IP + SSH (Linux) or WinRM (Windows)

8. **Difference between Ad-hoc commands and Playbooks?**
   → Ad-hoc = quick tasks, Playbook = structured automation

---



## 🛠️ Hands-on: Ansible with Multiple EC2 Instances

### 1️⃣ Install Ansible on Control Node

```bash
sudo apt update
sudo apt install ansible -y
ansible --version
```

---

### 2️⃣ Configure Passwordless SSH (Critical Step)

#### On Control Node

```bash
ssh-keygen -t ed25519
```

This generates:

* **Public key** → `~/.ssh/id_ed25519.pub`
* **Private key** → `~/.ssh/id_ed25519`

**Never copy the private key. Ever.**

Example public key format:

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIExampleKey ubuntu@control-node
```

Copy the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

---

#### On Target EC2 Instance

Edit authorized keys:

```bash
nano ~/.ssh/authorized_keys
```

* **Do NOT delete existing keys**
* Paste the new key on a **new line**

Fix permissions (mandatory):

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

---

#### Test SSH (Proof It Works)

From control node:

```bash
ssh ubuntu@<TARGET_PUBLIC_IP>
```

If it asks for a password, you messed up.

**Common mistakes:**

* Copied private key ❌
* Wrong user (`ubuntu` vs `ec2-user`) ❌
* Broken line breaks ❌
* Wrong permissions ❌

---

### 3️⃣ Create Inventory File (Control Node)

```bash
nano inventory
```

```ini
[servers]
<EC2_PUBLIC_IP>
```

---

### 4️⃣ Run Ad-hoc Command (Control Node)

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

## ❤️ Footer

<p align="center">
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Learning • Building • Improving
</p>

---

