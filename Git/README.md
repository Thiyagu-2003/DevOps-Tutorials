---

# ⭐ **GIT COMPLETE NOTES – BASIC → ADVANCED**

<p align="center">
  <img src="https://img.shields.io/badge/Git-Version%20Control-orange?logo=git&logoColor=white" />
  <img src="https://img.shields.io/badge/Level-Beginner%20to%20Advanced-blue" />
  <img src="https://img.shields.io/badge/Format-README.md-success" />
  <a href="https://github.com/Thiyagu-2003">
    <img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-brightgreen?logo=github" />
  </a>
</p>

---

# 📑 **Table of Contents**

1. [📌 Git Installation & Setup](#-1-git-installation--setup-basic)
2. [📁 Repositories (Init, Clone)](#-2-repositories-init-clone)
3. [🧱 Staging & Commits](#-3-staging--commits)
4. [🌿 Branching & Merging](#-4-branching--merging)
5. [🧩 Git Workflows](#-5-git-workflows-feature-release-hotfix)
6. [🤝 Collaboration](#-6-collaboration-push-pull-fork-pr)
7. [🚫 Gitignore & Cleaning](#-7-git-ignore--cleaning)
8. [🧠 Advanced Git Operations](#-8-advanced-operations)
9. [🎯 Common Interview Questions](#-9-common-interview-questions-straightforward-answers)
10. [👤 Author](#-author)
11. [❤️ Footer](#️-footer)

---

# 🟦 **1. Git Installation & Setup (BASIC)**

| Command                                            | Explanation                |
| -------------------------------------------------- | -------------------------- |
| `git --version`                                    | Check if Git is installed. |
| `git config --global user.name "Your Name"`        | Set global username.       |
| `git config --global user.email "you@example.com"` | Set global email.          |
| `git config --list`                                | View all Git configs.      |
| `git help <command>`                               | Git help for a command.    |

---

# 🟦 **2. Repositories (init, clone)**

## **BASIC**

| Command                       | Explanation                   |
| ----------------------------- | ----------------------------- |
| `git init`                    | Create a new repo.            |
| `git clone <repo-url>`        | Clone a remote repo.          |
| `git remote -v`               | List remotes.                 |
| `git remote add origin <url>` | Connect local repo to GitHub. |

## **INTERMEDIATE**

| Command                               | Explanation        |
| ------------------------------------- | ------------------ |
| `git remote remove origin`            | Remove remote.     |
| `git remote set-url origin <new-url>` | Update remote URL. |

---

# 🟦 **3. Staging & Commits**

## **BASIC**

| Command               | Explanation         |
| --------------------- | ------------------- |
| `git status`          | Show changed files. |
| `git add <file>`      | Stage a file.       |
| `git add .`           | Stage all files.    |
| `git commit -m "msg"` | Make a commit.      |
| `git log`             | Commit history.     |

## **INTERMEDIATE**

| Command                | Explanation                 |
| ---------------------- | --------------------------- |
| `git commit -am "msg"` | Add + commit tracked files. |
| `git diff`             | Unstaged changes.           |
| `git diff --staged`    | Staged changes.             |
| `git log --oneline`    | Short commit history.       |

## **ADVANCED**

| Command                     | Explanation              |
| --------------------------- | ------------------------ |
| `git reset <file>`          | Unstage file.            |
| `git reset --hard <commit>` | Reset & delete changes.  |
| `git revert <commit>`       | Reverse a commit safely. |

---

# 🟦 **4. Branching & Merging**

## **BASIC**

| Command                    | Explanation      |
| -------------------------- | ---------------- |
| `git branch`               | List branches.   |
| `git branch <name>`        | Create branch.   |
| `git checkout <branch>`    | Switch branch.   |
| `git checkout -b <branch>` | Create & switch. |

## **INTERMEDIATE**

| Command                  | Explanation         |
| ------------------------ | ------------------- |
| `git merge <branch>`     | Merge branch.       |
| `git branch -d <branch>` | Safe delete branch. |
| `git branch -D <branch>` | Force delete.       |

## **ADVANCED**

| Command                    | Explanation             |
| -------------------------- | ----------------------- |
| `git rebase <branch>`      | Linear clean history.   |
| `git cherry-pick <commit>` | Copy a specific commit. |
| `git stash`                | Save work temporarily.  |
| `git stash apply`          | Restore stash.          |
| `git stash pop`            | Restore + remove stash. |

---

# 🟦 **5. Git Workflows (Feature, Release, Hotfix)**

### **Feature Branch**

| Command                          | Explanation |
| -------------------------------- | ----------- |
| `git checkout -b feature/<name>` | New feature |
| `git push origin feature/<name>` | Upload      |
| `git merge feature/<name>`       | Merge       |

### **Release Workflow**

| Command                             | Explanation     |
| ----------------------------------- | --------------- |
| `git checkout -b release/<version>` | Release branch  |
| `git tag <tag>`                     | Version tagging |
| `git push origin --tags`            | Push all tags   |

### **Hotfix Workflow**

| Command                          | Explanation      |
| -------------------------------- | ---------------- |
| `git checkout -b hotfix/<issue>` | Quick fix branch |
| `git cherry-pick <commit>`       | Apply fix commit |

---

# 🟦 **6. Collaboration (Push, Pull, Fork, PR)**

## **BASIC**

| Command                    | Explanation   |
| -------------------------- | ------------- |
| `git push origin <branch>` | Push changes. |
| `git pull`                 | Pull & merge. |
| `git fetch`                | Fetch only.   |

## **INTERMEDIATE**

| Command                       | Explanation                 |
| ----------------------------- | --------------------------- |
| `git pull origin <branch>`    | Pull specific branch.       |
| `git push -u origin <branch>` | Push + set tracking branch. |

## **ADVANCED**

| Command             | Explanation             |
| ------------------- | ----------------------- |
| `git fetch --all`   | Fetch all branches.     |
| `git pull --rebase` | Clean update.           |
| `git push -f`       | Force push (dangerous). |

---

# 🟦 **7. Git Ignore & Cleaning**

## **BASIC**

| Action              | Explanation           |
| ------------------- | --------------------- |
| Create `.gitignore` | Ignore unwanted files |

## **INTERMEDIATE**

| Command                  | Explanation                            |
| ------------------------ | -------------------------------------- |
| `git rm --cached <file>` | Remove from tracking (keep in system). |

## **ADVANCED**

| Command        | Explanation             |
| -------------- | ----------------------- |
| `git clean -n` | Preview delete files.   |
| `git clean -f` | Delete untracked files. |

---

# 🟦 **8. Advanced Operations**

| Command                       | Explanation               |
| ----------------------------- | ------------------------- |
| `git reflog`                  | Full action history.      |
| `git bisect`                  | Binary search for bugs.   |
| `git submodule add <url>`     | Add sub-module repo.      |
| `git submodule update --init` | Init + update submodules. |

---

# 🟦 **9. Common Interview Questions (Straightforward Answers)**

### 1️⃣ What is Git?

A distributed version-control tool.

### 2️⃣ Git vs GitHub?

Git = tool, GitHub = hosting service.

### 3️⃣ What is a commit?

Snapshot of project.

### 4️⃣ What is a branch?

Parallel line of development.

### 5️⃣ Merge vs Rebase?

Merge keeps history; rebase cleans history.

### 6️⃣ What is a pull request?

Request to merge code on remote.

### 7️⃣ What is HEAD?

Pointer to current commit.

### 8️⃣ What is Git stash?

Temporary storage of changes.

### 9️⃣ What is a tag?

Permanent label for a version.

### 🔟 What is cherry-pick?

Apply a specific commit elsewhere.

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
