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

## 📚 **Table of Contents**

1. [🔧 Configuration Management Overview](#1-configuration-management-overview)
2. [❓ Why Ansible?](#2-why-ansible)
3. [📄 Ansible Basics](#3-ansible-basics)
4. [⚖️ Puppet vs Ansible](#4-puppet-vs-ansible)
5. [🧠 Key Advantages of Ansible](#5-key-advantages-of-ansible)
6. [🧩 Ansible Modules](#6-ansible-modules)
7. [📌 Ad-hoc Commands vs Playbooks](#7-ad-hoc-commands-vs-playbooks)
8. [❌ Limitations of Ansible](#8-limitations-of-ansible)
9. [🎯 Interview Questions & Answers](#9-interview-questions--answers)

10. [🛠️ Hands-on – Part 1: Ansible with Multiple EC2 Instances](#10-hands-on--part-1-ansible-with-multiple-ec2-instances)  
   - [10.1 Install Ansible on Control Node](#101-install-ansible-on-control-node)  
   - [10.2 Configure Passwordless SSH](#102-configure-passwordless-ssh)  
   - [10.3 Test SSH Connectivity](#103-test-ssh-connectivity)  
   - [10.4 Create Inventory File](#104-create-inventory-file)  
   - [10.5 Run First Ad-hoc Command](#105-run-first-ad-hoc-command)

11. [👤 Author](#11-author)

---

<a id="1-configuration-management-overview"></a>
## 1. 🔧 Configuration Management Overview

### 1.1 Configuration Management Tools

* **Ansible** (most widely used)
* Puppet
* Chef

Configuration management ensures **consistent system state**, **repeatable deployments**, and **reduced manual errors** across servers.

---

<a id="2-why-ansible"></a>
## 2. ❓ Why Ansible?

Ansible uses a **push-based architecture**.

* Configuration is written on a **control node**
* Changes are **pushed to target nodes** using SSH / WinRM
* No agents, no polling, no background daemons

This is why Ansible is simple, fast to adopt, and widely used.

---

<a id="3-ansible-basics"></a>
## 3. 📄 Ansible Basics

* Automation logic is written in **Playbooks**
* Playbooks use **YAML**
* Single commands → **Ad-hoc**
* Multi-step workflows → **Playbooks**

If your automation has more than one step and you’re still using ad-hoc commands, you’re doing it wrong.

---

<a id="4-puppet-vs-ansible"></a>
## 4. ⚖️ Puppet vs Ansible

| Feature        | Puppet         | Ansible                      |
|---------------|----------------|------------------------------|
| Mechanism     | Pull-based     | Push-based                   |
| Architecture  | Master / Agent | Agentless                    |
| Agent Needed  | Yes            | No                           |
| Node Setup    | Mandatory      | Not required                 |
| Authentication| Agent certs    | SSH / WinRM                  |
| Language      | Puppet DSL     | YAML                         |
| Adoption      | Declining      | Industry standard            |

---

<a id="5-key-advantages-of-ansible"></a>
## 5. 🧠 Key Advantages of Ansible

* Agentless → zero footprint
* Human-readable YAML
* Linux + Windows support
* Dynamic Inventory (cloud-native)
* Python-based extensibility
* Massive community via Ansible Galaxy

---

<a id="6-ansible-modules"></a>
## 6. 🧩 Ansible Modules

* Modules are execution units
* Mostly written in **Python**
* Custom modules are possible but rarely needed
* Community modules are shared via **Ansible Galaxy**

Writing shell scripts instead of modules is technical debt.

---

<a id="7-ad-hoc-commands-vs-playbooks"></a>
## 7. 📌 Ad-hoc Commands vs Playbooks

### 7.1 Ad-hoc Commands

* One-time actions
* No reusability
* No state tracking

```bash
ansible all -m shell -a "uptime"
````

### 7.2 Playbooks

* Multi-step automation
* Declarative
* Reusable and version-controlled

**Rule**

* One quick task → Ad-hoc
* Anything serious → Playbook

---

<a id="8-limitations-of-ansible"></a>

## 8. ❌ Limitations of Ansible

* Windows support is weaker than Linux
* Debugging complex playbooks is painful
* Slower at very large scale

At massive scale, Ansible alone is not enough.

---

<a id="9-interview-questions--answers"></a>

## 9. 🎯 Interview Questions & Answers

1. **What language is Ansible written in?**

   → Python

2. **Have you created a custom Ansible module?**
   
   → Yes, using Python (or explain conceptually if not)
   
3. **What language are playbooks written in?**
 
   → YAML

4. **What platforms does Ansible support?**
   
   → Linux (SSH) and Windows (WinRM)
   
5. **What mechanism does Ansible use?**

   → Push-based

6. **Why choose Ansible over other configuration tools?**
    
   → Agentless, push-based, simple YAML, fast setup
   
7. **Does Ansible require agents?**
    
   → No

8. **How does Ansible connect to Linux nodes?**
    
   → SSH

9. **How does Ansible connect to Windows nodes?**
    
   → WinRM

10. **Does Ansible support cloud providers?**
    
    → Yes, all major cloud providers (AWS, Azure, GCP)
    Requirement: Public IP + SSH (Linux) or WinRM (Windows)

11. **Difference between Ad-hoc commands and Playbooks?**
    
    → Ad-hoc = quick tasks, Playbook = structured automation


---

<a id="10-hands-on--part-1-ansible-with-multiple-ec2-instances"></a>

## 10. 🛠️ Hands-on – Part 1: Ansible with Multiple EC2 Instances

> This is mandatory. If this fails, Ansible will not work.

---

<a id="101-install-ansible-on-control-node"></a>

### 10.1 Install Ansible on Control Node

```bash
sudo apt update
sudo apt install ansible -y
ansible --version
```

---

<a id="102-configure-passwordless-ssh"></a>

### 10.2 Configure Passwordless SSH

#### On Control Node

```bash
ssh-keygen -t ed25519
```

* Public key → `~/.ssh/id_ed25519.pub`
* Private key → `~/.ssh/id_ed25519`

Never copy the private key.

```bash
cat ~/.ssh/id_ed25519.pub
```

---

#### On Target EC2 Instance 🖥

```bash
nano ~/.ssh/authorized_keys
```

* Do NOT remove existing keys
* Paste on a new line

Fix permissions:

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

---

<a id="103-test-ssh-connectivity"></a>

### 10.3 Test SSH Connectivity 🧪🛜

```bash
ssh ubuntu@<TARGET_PUBLIC_IP>
```

If it asks for a password, your setup is broken.

---

<a id="104-create-inventory-file"></a>

### 10.4 Create Inventory File 📁

```bash
nano inventory
```

```ini
[servers]
<EC2_PUBLIC_IP>
```

---

<a id="105-run-first-ad-hoc-command"></a>

### 10.5 Run First Ad-hoc Command 💨

```bash
ansible -i inventory all -m shell -a "touch devopsclass"
```

If this works, your Ansible setup is correct.

---

<a id="11-author"></a>

## 11. 👤 Author

```
Name    : Thiyagu S
Role    : Cloud & DevOps Learner
Country : India 🇮🇳
```

---

# ❤️ Footer

<p align="center">
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Learning • Building • Improving
</p>

---

