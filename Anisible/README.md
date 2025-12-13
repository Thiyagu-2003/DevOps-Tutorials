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

# 🔧 Configuration Management – Ansible

## Configuration Management Tools

* **Ansible** (most commonly used)
* Puppet
* Chef

---

## ❓ Why Ansible? (Why it’s preferred)

**Ansible uses a *push-based* mechanism.**
You write the configuration on the control node and push it to target servers—similar to how Git pushes code to a remote repository.

No agents, no constant polling. Simple and effective.

---

## 📄 Ansible Basics

* Ansible configuration files are called **Playbooks**
* One-time or simple tasks can be executed using **Ansible Ad-hoc commands**
* For multiple or complex tasks → **Use Playbooks**

---

## ⚖️ Puppet vs Ansible Comparison

| Feature        | Puppet            | Ansible                             |
| -------------- | ----------------- | ----------------------------------- |
| Mechanism      | Pull-based        | Push-based                          |
| Architecture   | Master / Slave    | Agentless                           |
| Agent Required | Yes               | No                                  |
| Configuration  | Required on nodes | Not required                        |
| Authentication | Agent setup       | SSH (Linux) / WinRM (Windows)       |
| Automation     | Mostly manual     | Fully automated (Dynamic Inventory) |
| OS Support     | Limited           | Linux + Windows                     |
| Language       | Puppet DSL        | YAML (simple & readable)            |
| Popularity     | Declining         | Widely adopted                      |

---

## 🧠 Key Advantages of Ansible

* Agentless (no installation on target nodes)
* Uses **YAML** → easy to read and write
* Supports **Linux and Windows**
* Supports **Dynamic Inventory**
* Custom modules can be written using **Python**
* Community roles available via **Ansible Galaxy**

---

## 🧩 Ansible Modules

* You can **write your own Ansible modules using Python**
* Modules can be shared using **Ansible Galaxy**

---

## 📌 Ad-hoc Commands vs Playbooks

* **Ad-hoc commands**

  * Used for quick, single tasks
  * Example: creating a file, checking uptime

* **Playbooks**

  * Used for multiple tasks and complex workflows
  * Declarative and reusable

👉 **Rule of thumb**

* 1–2 simple tasks → Ad-hoc
* Multiple tasks → Playbook

---

## ❌ Disadvantages of Ansible

* Windows support is weaker compared to Linux
* Debugging is difficult
* Performance issues in very large environments (parallel execution limits)

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

## 🛠️ Practical: Ansible with Multiple EC2 Instances

### 1️⃣ Install Ansible

```bash
sudo apt update
sudo apt install ansible -y
ansible --version
```

---

### 2️⃣ Enable Passwordless Authentication (SSH)

On Control Node:

```bash
ssh-keygen
```

Copy the public key:

```bash
cat ~/.ssh/id_rsa.pub
```

Paste it into the target EC2:

```bash
~/.ssh/authorized_keys
```

---

### 3️⃣ Create Inventory File

```bash
nano inventory
```

```ini
[servers]
<EC2_PUBLIC_IP>
```

---

### 4️⃣ Run Ad-hoc Command

```bash
ansible -i inventory all -m shell -a "touch devopsclass"
```

---

# 👤 **Author**

```
Name: Thiyagu S
Role: Cloud & DevOps Learner
Country: India 🇮🇳
```

---

# ❤️ **Footer**

<p align="center">
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Learning • Building • Improving
</p>

---


