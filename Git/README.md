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
10. [📎 Footer](#-footer)

---

# 🟦 **1. Git Installation & Setup (BASIC)**

| Command                                            | Explanation                 |
| -------------------------------------------------- | --------------------------- |
| `git --version`                                    | Checks if Git is installed. |
| `git config --global user.name "Your Name"`        | Sets global username.       |
| `git config --global user.email "you@example.com"` | Sets global email.          |
| `git config --list`                                | Shows all Git configs.      |
| `git help <command>`                               | Shows help for a command.   |

---

# 🟦 **2. Repositories (init, clone)**

## **BASIC**

| Command                       | Explanation                    |
| ----------------------------- | ------------------------------ |
| `git init`                    | Creates a new Git repository.  |
| `git clone <repo-url>`        | Copies a remote repo locally.  |
| `git remote -v`               | Lists connected remotes.       |
| `git remote add origin <url>` | Connects local repo to GitHub. |

## **INTERMEDIATE**

| Command                               | Explanation         |
| ------------------------------------- | ------------------- |
| `git remote remove origin`            | Removes a remote.   |
| `git remote set-url origin <new-url>` | Changes remote URL. |

---

# 🟦 **3. Staging & Commits**

## **BASIC**

| Command               | Explanation                |
| --------------------- | -------------------------- |
| `git status`          | Shows changes.             |
| `git add <file>`      | Stages a file.             |
| `git add .`           | Stages all modified files. |
| `git commit -m "msg"` | Creates a commit.          |
| `git log`             | Shows commit history.      |

## **INTERMEDIATE**

| Command                | Explanation                   |
| ---------------------- | ----------------------------- |
| `git commit -am "msg"` | Adds + commits tracked files. |
| `git diff`             | Shows unstaged changes.       |
| `git diff --staged`    | Shows staged changes.         |
| `git log --oneline`    | Compact commit history.       |

## **ADVANCED**

| Command                     | Explanation                            |
| --------------------------- | -------------------------------------- |
| `git reset <file>`          | Unstages file.                         |
| `git reset --hard <commit>` | Resets repo + deletes changes.         |
| `git revert <commit>`       | Creates new commit undoing old commit. |

---

# 🟦 **4. Branching & Merging**

## **BASIC**

| Command                    | Explanation                |
| -------------------------- | -------------------------- |
| `git branch`               | Lists branches.            |
| `git branch <name>`        | Creates branch.            |
| `git checkout <branch>`    | Switches branch.           |
| `git checkout -b <branch>` | Creates + switches branch. |

## **INTERMEDIATE**

| Command                  | Explanation            |
| ------------------------ | ---------------------- |
| `git merge <branch>`     | Merges given branch.   |
| `git branch -d <branch>` | Deletes branch safely. |
| `git branch -D <branch>` | Force deletes branch.  |

## **ADVANCED**

| Command                    | Explanation                     |
| -------------------------- | ------------------------------- |
| `git rebase <branch>`      | Rewrites history cleanly.       |
| `git cherry-pick <commit>` | Copy specific commit to branch. |
| `git stash`                | Temporarily store changes.      |
| `git stash apply`          | Restore stash.                  |
| `git stash pop`            | Restore + delete stash.         |

---

# 🟦 **5. Git Workflows (Feature, Release, Hotfix)**

## **Feature Branch Workflow**

| Command                          | Explanation           |
| -------------------------------- | --------------------- |
| `git checkout -b feature/<name>` | Create feature branch |
| `git push origin feature/<name>` | Push feature          |
| `git merge feature/<name>`       | Merge feature         |

## **Release Workflow**

| Command                             | Explanation           |
| ----------------------------------- | --------------------- |
| `git checkout -b release/<version>` | Create release branch |
| `git tag <tag>`                     | Tag a version         |
| `git push origin --tags`            | Push all tags         |

## **Hotfix Workflow**

| Command                          | Explanation               |
| -------------------------------- | ------------------------- |
| `git checkout -b hotfix/<issue>` | Create hotfix branch      |
| `git cherry-pick <commit>`       | Apply specific fix commit |

---

# 🟦 **6. Collaboration (Push, Pull, Fork, PR)**

## **BASIC**

| Command                    | Explanation          |
| -------------------------- | -------------------- |
| `git push origin <branch>` | Push branch.         |
| `git pull`                 | Pull latest changes. |
| `git fetch`                | Fetch without merge. |

## **INTERMEDIATE**

| Command                       | Explanation                |
| ----------------------------- | -------------------------- |
| `git pull origin <branch>`    | Pull specific branch.      |
| `git push -u origin <branch>` | First push + set upstream. |

## **ADVANCED**

| Command             | Explanation                          |
| ------------------- | ------------------------------------ |
| `git fetch --all`   | Fetch all branches.                  |
| `git pull --rebase` | Clean pull with rebase.              |
| `git push -f`       | Force push (rewrite remote history). |

---

# 🟦 **7. Git Ignore & Cleaning**

## **BASIC**

| Action              | Explanation                  |
| ------------------- | ---------------------------- |
| Create `.gitignore` | Exclude files from tracking. |

## **INTERMEDIATE**

| Command                  | Explanation                          |
| ------------------------ | ------------------------------------ |
| `git rm --cached <file>` | Remove from tracking (keep locally). |

## **ADVANCED**

| Command        | Explanation             |
| -------------- | ----------------------- |
| `git clean -n` | Preview deletions.      |
| `git clean -f` | Delete untracked files. |

---

# 🟦 **8. Advanced Operations**

| Command                       | Explanation                          |
| ----------------------------- | ------------------------------------ |
| `git reflog`                  | Shows all actions including removed. |
| `git bisect`                  | Find bug using binary search.        |
| `git submodule add <url>`     | Add submodule repo.                  |
| `git submodule update --init` | Init & update submodules.            |

---

# 🟦 **9. Common Interview Questions (Straightforward Answers)**

### **1. What is Git?**

A distributed version control system.

### **2. Git vs GitHub?**

Git = VCS tool; GitHub = cloud hosting for Git repos.

### **3. What is a commit?**

A snapshot of your code.

### **4. What is a branch?**

A parallel line of development.

### **5. Merge vs Rebase?**

Merge = keeps history; Rebase = rewrites into clean linear history.

### **6. What is a pull request?**

A request to merge your branch into another branch on remote.

### **7. What is HEAD?**

Pointer to current branch/commit.

### **8. What is stash?**

Temporary storage of uncommitted work.

### **9. What is a tag?**

Permanent label for important commits.

### **10. What is cherry-pick?**

Copy a specific commit to another branch.

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
