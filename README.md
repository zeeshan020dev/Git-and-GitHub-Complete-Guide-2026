<div align="center">

# Git & GitHub Handbook
### The Complete Beginner's Guide — Master Version Control, Collaborate Better, Code with Confidence

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Beginner Friendly](https://img.shields.io/badge/Level-Beginner%20Friendly-brightgreen?style=for-the-badge)

</div>

---

## 📑 Table of Contents

1. [Introduction](#1-introduction)
2. [What is Git?](#2-what-is-git)
3. [Understanding Version Control Systems](#3-understanding-version-control-systems)
4. [Git vs GitHub](#4-git-vs-github)
5. [Installing Git](#5-installing-git)
6. [How Git Works](#6-how-git-works)
7. [Hands-on Git](#7-hands-on-git)
8. [Git Scenario 1: Single User Setup](#8-git-scenario-1-single-user-setup)
9. [Ignoring Files](#9-ignoring-files)
10. [Tracking Empty Directories](#10-tracking-empty-directories)
11. [Branches](#11-branches)
12. [Merge Conflict](#12-merge-conflict)
13. [Stashing in Git](#13-stashing-in-git)
14. [Git Tags](#14-git-tags)
15. [Git Rebase](#15-git-rebase)
16. [Using GitHub to Host Our Repositories](#16-using-github-to-host-our-repositories)
17. [GitHub Desktop: GUI for Git and GitHub](#17-github-desktop-gui-for-git-and-github)
18. [Using Git in VS Code](#18-using-git-in-vs-code)
19. [Git Scenario 2: Multi-User Setup](#19-git-scenario-2-multi-user-setup)
20. [Modern Workflow](#20-modern-workflow)
21. [Conclusion](#21-conclusion)

---

## 1. Introduction

### Welcome to the **Git & GitHub Handbook** 👋

Learning Git doesn’t have to be hard. This handbook is a **beginner-friendly, practical guide** to help you understand **Git and GitHub from scratch** without the jargon.

If you’ve ever asked **“What is Git?”**, **“What is a commit?”**, or **“How do developers work together on GitHub?”**, you’re in the right place. You’ll find clear explanations, visual diagrams, real-world examples, and copy-paste-ready commands to make learning easy.

By the end of this handbook, you’ll know how to:

- 🚀 Track and manage code with Git.
- 🌿 Create and use branches.
- 🔀 Merge changes and fix conflicts.
- 🤝 Collaborate with others on GitHub.
- 💼 Use real-world Git workflows.

Whether you’re a **student**, **self-taught developer**, **open-source contributor**, or **preparing for your first tech job**, this handbook is for you.

You can use this handbook in two ways:

- 📖 **Learn step by step** by reading it from start to finish.
- 🔍 **Use it as a reference** by jumping to any of the **topics** in the [Table of Contents](#-table-of-contents) whenever you need a quick refresher.

> **⭐ Found this handbook helpful?** Consider starring the repository to support the project, and feel free to open a pull request if you'd like to improve it for the community.

---

## 2. What is Git?

**Git** is a version control system that tracks changes to files over time. It helps you save progress, return
to earlier versions, and work without losing important edits.

Think of Git as a timeline for your project. Each saved point is called a commit. You can review
changes, compare versions, and undo mistakes when needed.

### 📌 A Commit Timeline

```mermaid
flowchart LR
    A["🔴 A<br/>Commit 1"] --> B["🟠 B<br/>Commit 2"] --> C["🟢 C<br/>Commit 3"]
```

> In the above diagram, each letter is one commit. New commits extend the line to the right.

Git is often used with **GitHub**, which gives you a place to store repositories online, share code, and collaborate with others.

### 🚀 Use Git When You Want

<table>
<tr>
<td width="50%">

### 01 📜 Keep a Complete History

A clear history of changes made to your project over time

</td>

<td width="50%">

### 02 💾 Create Reliable Backups

Safe backup points for your work that you can return to anytime.

</td>
</tr>

<tr>
<td>

### 03 🤝 Collaborate with Teams

Easier teamwork when multiple people work on the same project.

</td>

<td>

### 04 🔄 Undo Mistakes Safely

The ability to undo mistakes without losing important edits.

</td>
</tr>
</table>

### 🔄 Visualizing a Simple Git Workflow

| Step | Action | Git Command |
|:---:|:--------|:-----------|
| ✏️ | **Edit Files** | Working Directory |
| ⬇️ | **Stage Changes** | `git add` |
| 💾 | **Create Commit** | `git commit` |
| ☁️ | **Push to GitHub** | `git push` |
| 🌍 | **Repository Updated** | GitHub |

```mermaid
flowchart LR
    A["✏️ Edit Files<br/><sub>Working Directory</sub>"]
    --> B["📋 Stage Changes<br/><code>git add</code>"]
    --> C["💾 Commit Changes<br/><code>git commit</code>"]
    --> D["☁️ Push to GitHub<br/><code>git push</code>"]
    --> E["🌍 GitHub Repository"]
```

---

## 3. Understanding Version Control Systems

Version control systems (VCS) track file changes over time. They let you save snapshots, compare versions, and collaborate without overwriting each other's work.

With version control, you can:

- 📝 Save snapshots of your project.
- 🔍 Compare different versions.
- ⏪ Restore previous versions when needed.
- 🤝 Collaborate with others without overwriting each other's work.

---

### 🏛️ Centralized Version Control System (CVCS)

In a centralized model, one server holds the official copy of the project. Developers check out files, make changes, and check them back in.

### Examples

- SVN (Subversion)
- CVS (Concurrent Versions System)

### Downside

- If the central server goes down, collaboration stops

---

### 🌐 Distributed Version Control System (DVCS)

In a distributed model, every developer has a full copy of the project history on their machine. You commit locally first, then sync with a remote when ready.

### Examples

- Git
- Mercurial

### ✅ Benefit

- You can work offline and still have a full history.

---

## ⚖️ Centralized vs Distributed

| Feature | 🏛️ Centralized VCS | 🌐 Distributed VCS |
|----------|-------------------|--------------------|
| 📜 Project History | Stored only on the server | Stored on every developer's machine |
| 💻 Offline Work | Limited | Full support |
| 💾 Backup | Only the server has the complete history | Every clone acts as a backup |
| ⚠️ Failure Risk | Single point of failure | Multiple copies reduce risk |
| ⚡ Performance | Slower (depends on server) | Faster local operations |

---

## 📊 Visual Comparison

```text
🏛️ Centralized Version Control

            ☁️ Central Server
          ┌─────────────────┐
          │ Project History │
          └────────┬────────┘
          ┌────────┼────────┐
          ▼        ▼        ▼
      👨‍💻 Dev A 👩‍💻 Dev B 👨‍💻 Dev C

```

```text
🌐 Distributed Version Control (Git)

👨‍💻 Dev A      👩‍💻 Dev B      👨‍💻 Dev C
┌──────────┐  ┌──────────┐  ┌──────────┐
│ Full Repo│  │ Full Repo│  │ Full Repo│
│ + History│  │ + History│  │ + History│
└────┬─────┘  └────┬─────┘  └────┬─────┘
     └─────────────┼─────────────┘
                   ▼
          ☁️ Remote Repository
```

---

### 🚀 Why Git Uses a Distributed Model

Git was created by **Linus Torvalds** in **2005** for large teams working on the **Linux Kernel**. A distributed model means:

- ⚡ Faster performance
- 💾 Reliable backups
- 🌿 Easy branching
- 🔀 Powerful merging
- 💻 Offline development
- 🤝 Efficient collaboration

---

### 📝 In Short

- Centralized VCS relies on one server.
- Distributed VCS gives everyone a full copy.
- Git is distributed by design.

---

## 4. Git vs GitHub

**Git** is the version control tool that runs on your computer. It tracks changes, creates commits, and manages branches.

**GitHub** is a website that hosts Git repositories online. It adds collaboration features like pull requests,
issues, and code review.

They are **not** the same thing — Git is the engine, GitHub is one of several places you can park it.

### 📁 Git Repository

A repository (repo) is a project folder tracked by Git. It contains your files plus the hidden **.git** folder with all history. 

---

### 🖥️ Local Repository vs ☁️ Remote Repository

- **Local repo:** on your machine, where you commit daily work.
- **Remote repo:** on GitHub (or similar), where you push and pull to share code.

---

### 📝 In Short

- 📁 A **Git Repository** is a project folder managed by Git.
- 📂 The hidden **`.git`** folder stores your project's complete history.
- 🖥️ A **Local Repository** is where you develop and commit your work.
- ☁️ A **Remote Repository** is where you share, back up, and collaborate on your project.
- 🔄 Use **`git push`** to upload your commits and **`git pull`** to download the latest changes.

### Git vs GitHub Comparison


| | Git | GitHub |
|---|---|---|
| What it is | Tool | Hosting service |
| Runs on | Your computer | The cloud |
| Needs internet | No (for local work) | Yes (to sync) |
| Stores history | Yes | Yes (as a remote copy) |

---

## 5. Installing Git

Before you can start tracking your projects with Git, you need to install it on your operating system. Git is available for **Windows**, **macOS**, and **Linux**, and the installation process only takes a few minutes.

> 💡 **Recommendation:** Always install Git from the **official Git website** to ensure you get the latest stable version.

---

### 🪟 Installing Git on Windows

#### Method 1: Download from the Official Website (Recommended)

1. Visit **https://git-scm.com/downloads**
2. Download the latest version for **Windows**.
3. Run the installer.
4. Leave all settings as **Default** unless you have specific preferences.
5. Click **Next** until the installation is complete.
6. Click **Finish**.

✅ Git is now installed on your computer.

---

#### Method 2: Install Using Winget

If you have **Windows Package Manager (Winget)** installed, open **Command Prompt** or **PowerShell** and run:

```bash
winget install --id Git.Git -e --source winget
```

Wait for the installation to complete.

---

### 🍎 Installing Git on macOS

There are two common ways to install Git on macOS.

#### Method 1: Install Xcode Command Line Tools (Recommended)

Open **Terminal** and run:

```bash
xcode-select --install
```

Follow the on-screen instructions.

Git will be installed automatically along with Apple's Command Line Tools.

---

#### Method 2: Install Using Homebrew

If you already have **Homebrew** installed, simply run:

```bash
brew install git
```

---

### 🐧 Installing Git on Linux

Git is available through your Linux distribution's package manager.

#### Debian / Ubuntu

Update your package list:

```bash
sudo apt update
```

Install Git:

```bash
sudo apt install git
```

---

#### Fedora

```bash
sudo dnf install git
```

---

#### Arch Linux

```bash
sudo pacman -S git
```

---

### ✅ Verify the Installation

After installing Git, open your terminal (or Command Prompt) and run:

```bash
git --version
```

If Git is installed correctly, you'll see output similar to:

```text
git version 2.x.x
```

> 🎉 Congratulations! Git has been successfully installed.

---

### 🛠️ Choosing Your Git Workflow

Once Git is installed, you can use it in different ways depending on your preference.

| Workflow | Best For | Description |
|----------|----------|-------------|
| 💻 **Command Line** | ⭐ Recommended | The most powerful and flexible way to use Git. Works on every platform and supports every Git feature. |
| 📝 **Visual Studio Code** | Daily Development | Use VS Code's built-in **Source Control** panel to manage commits, branches, and repositories without leaving your editor. |
| 🖥️ **GitHub Desktop** | Beginners | A simple graphical interface that lets you use Git without memorizing commands. |

> 💡 **Good to Know:** Regardless of whether you use the **Command Line**, **VS Code**, or **GitHub Desktop**, they all execute the **same Git commands** behind the scenes.

---

### ⚡ Quick Installation Summary

| Platform | Installation Method | Command / Website |
|----------|---------------------|-------------------|
| 🪟 **Windows** | Official Installer | https://git-scm.com/downloads |
| 🪟 **Windows** | Winget | `winget install --id Git.Git -e --source winget` |
| 🍎 **macOS** | Xcode Command Line Tools | `xcode-select --install` |
| 🍎 **macOS** | Homebrew | `brew install git` |
| 🐧 **Debian / Ubuntu** | APT | `sudo apt update && sudo apt install git` |
| 🐧 **Fedora** | DNF | `sudo dnf install git` |
| 🐧 **Arch Linux** | Pacman | `sudo pacman -S git` |

---

## 6. How Git Works

Git moves your changes through **four areas** before they reach GitHub:

---

### The Four Areas of Git

| 📁 | 📋 | 💾 | ☁️ |
|:--:|:--:|:--:|:--:|
| **WORKING DIR** | **STAGING AREA** | **LOCAL REPO** | **REMOTE REPO** |
| Your files on disk | Changes queued for commit | Commits saved locally | GitHub / cloud host |

---

| **01) Working Directory**<br><br>Your project files on disk. Edit freely here. Git sees changes but does not save them until you stage and commit. | **02) Staging Area**<br><br>A holding zone for changes you want in the next commit. Use `git add` to move files here. |
|:---|:---|
| **03) Local Repository**<br><br>Where commits are stored permanently on your machine. Use `git commit` to save a snapshot. | **04) Remote Repository**<br><br>The copy on GitHub (or another host). Use `git push` to upload and `git pull` to download. |

### The Git Workflow

A full cycle from editing to pushing looks like this:

```bash
# 1. Edit files in your working directory

# 2. Stage changes
git add .

# 3. Commit to local repository
git commit -m "describe your change"

# 4. Push to remote repository
git push origin main
```

### Understanding Snapshots

Each commit is a snapshot of your entire project at one moment. Git stores these efficiently so that you can jump back to any point in history.

```bash
# See all snapshots
git log --oneline
```

---

## 7. Hands-on Git

Git provides a simple set of commands for tracking changes, saving versions of your work, and reviewing your project history.

### Basic Git Checks

Before working with Git, you can verify that Git is installed and check the current state of your repository.

```bash
# check installed Git version
git --version

# initialize Git in the current folder
git init

# check the current repository state
git status
```

### Set Your Git Identity

Before making your first commit, configure your name and email address. You usually need to do this only **once per machine**.

```bash
git config --global user.name "Your_Name"
git config --global user.email "Your_Email"
```

You can verify your configuration with:

```bash
git config --global user.name
git config --global user.email
```

---

### 🔑 The Big Four Git Commands

These four commands cover most of your everyday Git workflow:

1. `git status`
2. `git add`
3. `git commit`
4. `git log`

---

### 1. `git status`

Shows the **current state of your repository**.

It tells you which files are:

- Modified
- Staged
- Untracked
- Ready to commit

```bash
git status
```

For a shorter and more compact output:

```bash
git status -s
```

Example:

```text
M  README.md
?? notes.txt
```

Here:

- `M` means the file has been modified.
- `??` means Git is not yet tracking the file.

---

### 2. `git add`

Stages changes so they can be included in your **next commit**.

#### Stage one file

```bash
git add README.md
```

#### Stage multiple files

```bash
git add README.md main.py
```

#### Stage all changes

```bash
git add .
```

#### Stage all files of one type

```bash
git add *.py
```

> **Note:** `git add` does not permanently save your changes. It only moves them into the **staging area**, ready for the next commit.

---

### 3. `git commit`

Creates a **saved snapshot** of your staged changes.

```bash
git commit -m "add README file"
```

A good commit message should briefly explain what changed.

Example:

```bash
git commit -m "fix login validation"
```

You can also stage and commit **already tracked files** in one command:

```bash
git commit -am "fix typo in main script"
```

> **Important:**  
> `git commit -am` only works with files that Git is **already tracking**.  
> New or untracked files must first be staged using `git add`.

Example:

```bash
git add new_file.py
git commit -m "add new Python file"
```

---

### 4. `git log`

Shows the **commit history** of your repository.

#### Full commit history

```bash
git log
```

#### Compact one-line history

```bash
git log --oneline
```

Example:

```text
a1b2c3d add README file
e4f5g6h fix login validation
7h8i9j0 initial commit
```

#### Show the last 5 commits

```bash
git log --oneline -5
```

#### Display branch and merge history as a graph

```bash
git log --oneline --graph --all
```

This is especially useful when working with **multiple branches**.

---

### The Basic Git Lifecycle

A normal Git workflow usually follows this cycle:

```bash
# 1. check what changed
git status

# 2. stage your changes
git add .

# 3. save the staged changes
git commit -m "describe your changes"

# 4. review commit history
git log --oneline
```

**Think of it as:**

`Check → Stage → Save → Review`

---

### More Useful Everyday Commands

#### Unstage a file

Removes a file from the staging area without deleting your changes.

```bash
git restore --staged <filename>
```

Example:

```bash
git restore --staged README.md
```

#### Stage everything

```bash
git add .
```

#### View compact history

```bash
git log --oneline
```

#### View graphical history

```bash
git log --oneline --graph --all
```

---

### Command Reference at a Glance

| Command | What It Does |
|---|---|
| `git init` | Initializes a new Git repository in the current folder. |
| `git status` | Shows staged, modified, and untracked files in the working directory. |
| `git status -s` | Displays a compact summary of the repository state. |
| `git add <filename>` | Stages a specific file for the next commit. |
| `git add .` | Stages all current changes for the next commit. |
| `git add *.py` | Stages all matching `.py` files. |
| `git commit -m "message"` | Creates a new snapshot with a descriptive message. |
| `git commit -am "message"` | Stages tracked modified files and commits them in one step. |
| `git log` | Displays the complete commit history. |
| `git log --oneline` | Displays each commit in a compact one-line format. |
| `git log --oneline -5` | Displays the five most recent commits. |
| `git log --oneline --graph --all` | Visualizes branch and merge history as a graph. |
| `git restore --staged <filename>` | Removes a file from staging while keeping its changes. |

---

## 8. Git Scenario 1: Single User Setup

Let me walk you through a complete project from scratch.

### Complete Walkthrough

**1. Create a Simple Project**

```bash
mkdir hello-git
cd hello-git
git init
echo "# Hello Git" > README.md
````

**2. Make Changes**

```bash
echo "print('hello')" > main.py
git status
```

**3. Stage Files**

```bash
git add README.md
git add main.py

# or stage everything at once
git add .
```

**4. Create a Commit**

```bash
git commit -m "initial commit with readme and main script"
```

---

### Viewing History

```bash
git log --oneline
```

---

### Best Practices While Committing

* Commit when a logical piece of work is done.
* One idea per commit.
* Use present tense messages: `add login form` not `added login form`.

```bash
# good commit flow
git status
git add .
git commit -m "add user input validation"
git log --oneline -3
```

---

### The Full Workflow in One View

Every project follows the same repeating loop: **edit → stage → commit → review**. Repeat this cycle for every logical change.

**EDIT**

Make your changes to files in the working directory. Git notices but does not save them yet.

**STAGE**

Use `git add` to move changes into the staging area, ready to be committed.

**COMMIT**

Use `git commit -m` to save a permanent snapshot with a clear message.

**REVIEW**

Use `git log --oneline` to inspect your commit history and confirm everything looks right.

---

## 9. Ignoring Files

Not every file belongs in Git. Some files should stay local and should never be committed to your repository.

### Why Some Files Should Not Be Tracked

Common examples include:

- Passwords and API keys such as `.env`
- Dependency folders such as `node_modules/`
- Build output such as `dist/` and `build/`
- Python-generated files such as `__pycache__/`
- Operating system files such as `.DS_Store` and `Thumbs.db`
- Large or temporary data files

---

### Understanding `.gitignore`

Create a `.gitignore` file in the root of your repository. Git will ignore files and folders that match the patterns listed inside it.

```bash
touch .gitignore
````

Example `.gitignore` file:

```gitignore
# environment variables
.env

# Python
__pycache__/
*.pyc
venv/

# OS files
.DS_Store
Thumbs.db

# build output
dist/
build/
```

---

### Common `.gitignore` Rules

Ignore a specific file:

```gitignore
secret.txt
```

Ignore a folder and everything inside it:

```gitignore
node_modules/
```

Ignore all files of a specific type:

```gitignore
*.log
```

Ignore all `.log` files but keep one specific file:

```gitignore
*.log
!important.log
```

The `!` symbol means **do not ignore this matching file**.

So:

```gitignore
!important.log
```

means that `important.log` should remain trackable even if `*.log` is ignored above it.

---

### Pattern Reference

| Pattern          | What It Ignores                                                           |
| ---------------- | ------------------------------------------------------------------------- |
| `secret.txt`     | A file named `secret.txt` wherever the pattern matches in the repository. |
| `node_modules/`  | The `node_modules` folder and everything inside it.                       |
| `*.log`          | All files with the `.log` extension.                                      |
| `!important.log` | Keeps `important.log` from being ignored when a previous rule ignores it. |
| `.env`           | The environment file that often contains secrets and API keys.            |
| `__pycache__/`   | Python cache directories.                                                 |
| `*.pyc`          | Compiled Python files.                                                    |
| `dist/`          | Distribution or build output folder.                                      |
| `build/`         | Build output folder.                                                      |

---

### Empty Folders and `.gitkeep`

Git does not track empty folders by itself.

If you want an empty folder to appear in your repository, add a placeholder file such as `.gitkeep`.

```bash
mkdir logs
touch logs/.gitkeep
git add logs/.gitkeep
```

`.gitkeep` is not a special Git feature. It is simply a common convention used to keep otherwise-empty folders in a repository.

---

### Already Tracking a File?

Adding a file to `.gitignore` does not automatically stop Git from tracking it if it was already committed or staged before.

Remove it from Git's tracking while keeping the local file:

```bash
git rm --cached filename
```

Then commit the change:

```bash
git commit -m "stop tracking filename"
```

For example:

```bash
git rm --cached .env
git commit -m "stop tracking .env"
```

The file will remain on your computer, but Git will stop tracking it.

---


## 10. Tracking Empty Directories

Git only tracks **files**, never empty folders. To keep an empty folder (like `logs/`) in your repo:

```bash
mkdir logs
touch logs/.gitkeep
git add logs/.gitkeep
```

---

## 11. Branches

Branches let you work on new features, bug fixes, or experiments without touching your stable code.

### What is a Branch?

A branch is an independent line of development.

In most repositories, `main` is the default branch.

Branching at commit `B` lets you build a feature without changing `main`:

```text
A─B─C        main
   \
    D─E      feature/search
````

Each letter represents a commit.

The lines show how commits are connected, and time flows from left to right.

---

### Why Branches Exist

Branches are useful because:

* They let you build features in isolation.
* They help fix bugs without breaking stable or production code.
* They let you experiment safely.
* They allow multiple lines of development to exist at the same time.

---

### Creating a Branch

Create a new branch with:

```bash
git branch feature/search         # git branch <branchname>
```

This creates the branch, but it does not switch you to it.

---

### Switching Branches

Using the traditional command:

```bash
git checkout feature/search
```

Modern alternative:

```bash
git switch feature/search
```

Both commands move you onto the selected branch.

---

### Creating and Switching Together

You can create a branch and switch to it in one command.

Traditional method:

```bash
git checkout -b feature/search
```

Modern alternative:

```bash
git switch -c feature/search
```

The `-c` option tells Git to create the branch before switching to it.

---

### Viewing Branches

Show all local branches:

```bash
git branch
```

Example:

```text
* feature/search
  main
```

The `*` symbol shows your current branch.

Show local and remote branches:

```bash
git branch -a
```

Show only the name of your current branch:

```bash
git branch --show-current
```

Example:

```text
feature/search
```

---

### Understanding the Git Graph

You can visualize how branches split and merge with:

```bash
git log --oneline --graph --all
```

A typical branch history may look like:

```text
      D─E
     /   \
A─B─C─────M
```

Here:

* `A`, `B`, and `C` are commits on the original line of development.
* `D` and `E` represent work done on another branch.
* `M` is a merge commit where the two lines of development come back together.

This graph helps you understand how branches have changed and merged over time.

---

## 12. Merge Conflict

Merge conflicts happen when Git cannot automatically combine changes made to the same lines of a file.

### Why Conflicts Happen

Common causes include:

- Two people edit the same line of a file.
- You edit a file locally while someone else pushes changes to the same part.
- You merge branches that contain overlapping edits.
- You rebase a branch that has conflicting changes.

For example, both branches may change the same line after splitting from the same commit:

```text
      C   feature/search changed line 10
     /
A─B─E    main also changed line 10
````

Both branches changed the same part of the file after commit `B`.

Git cannot decide automatically which version should be kept, so it reports a **merge conflict**.

---

### Resolving a Merge Conflict

Try to merge the branch:

```bash
git merge feature/search
```

If Git finds conflicting changes, you may see output similar to:

```text
CONFLICT (content): Merge conflict in filename.py
```

Open the conflicted file and Git will show special conflict markers.

---

### Conflict Markers

A conflicted file may look like this:

```text
<<<<<<< HEAD
your version
=======
their version
>>>>>>> feature/search
```

The markers mean:

* `<<<<<<< HEAD` shows the version from your current branch.
* `=======` separates the two conflicting versions.
* `>>>>>>> feature/search` shows the version from the branch being merged.

Edit the file manually and keep the correct code.

Then remove all conflict markers:

```text
<<<<<<< HEAD
=======
>>>>>>> feature/search
```

After resolving the file, stage it:

```bash
git add filename.py
```

Then create a commit:

```bash
git commit -m "resolve merge conflict in filename.py"
```

---

### Understanding `git diff`

`git diff` helps you inspect changes before committing them.

It can compare different areas of your Git workflow.

```text
Working Directory → Staging Area → Repository
```

#### View Unstaged Changes

Compare your working directory with the staging area:

```bash
git diff
```

This shows changes you have made but have not staged yet.

---

#### View Staged Changes

Compare the staging area with the last commit (`HEAD`):

```bash
git diff --staged
```

This shows changes that have already been staged with `git add`.

---

#### View Changes in a Specific File

```bash
git diff filename.py
```

During a merge conflict, this can help you inspect conflicting changes in a specific file.

---

### Quick `git diff` Reference

| Command                | What It Compares                     |
| ---------------------- | ------------------------------------ |
| `git diff`             | Working directory vs staging area    |
| `git diff --staged`    | Staging area vs last commit (`HEAD`) |
| `git diff filename.py` | Changes in a specific file           |

---

### Best Practices to Avoid Conflicts

Pull the latest changes before starting work:

```bash
git pull origin main
```

Before pushing your work, make sure your local branch is updated:

```bash
git pull origin main
git push origin main
```

Other good practices include:

* Keep feature branches short-lived.
* Commit and synchronize changes regularly.
* Communicate with teammates when working on the same files.
* Avoid making large unrelated changes in the same commit.

---

### Abort a Merge if You Are Stuck

If you are in the middle of a merge conflict and want to cancel the merge:

```bash
git merge --abort
```

`git merge --abort` stops the in-progress merge and attempts to return your files to the state they were in before you ran:

```bash
git merge
```

---

## 13. Stashing in Git

Git stash saves uncommitted work temporarily so you can switch tasks without creating a half-finished commit.

### Why Git Stash Exists

Suppose you are working on a feature, but suddenly need to fix an urgent bug on `main`.

Instead of committing unfinished work, you can temporarily store your changes using Git stash.

```text
Working on feature
      ↓
git stash
      ↓
Switch branch / fix bug
      ↓
Return to feature
      ↓
git stash pop
````

---

### Saving Work Temporarily

Save your current uncommitted changes:

```bash
git stash
```

You can also add a message so you remember what the stash contains:

```bash
git stash push -m "wip on search feature"
```

This temporarily stores your work and gives you a cleaner working directory.

---

### Viewing Stashes

To see all saved stashes:

```bash
git stash list
```

Example:

```text
stash@{0}: On feature/search: wip on search feature
stash@{1}: On feature/login: half-done login form
```

Each stash receives an identifier such as:

```text
stash@{0}
stash@{1}
```

---

### Restoring a Stash

Apply the most recent stash:

```bash
git stash apply
```

This restores the changes but keeps the stash in the stash list.

To apply a specific stash:

```bash
git stash apply stash@{1}
```

---

### Applying vs Popping

`git stash apply` restores the saved changes but keeps the stash:

```bash
git stash apply
```

`git stash pop` restores the saved changes and removes the stash from the list:

```bash
git stash pop
```

In simple terms:

```text
git stash apply → restore + keep
git stash pop   → restore + remove
```

---

### Real-World Example

Suppose you are working on a login feature but need to fix an urgent issue on `main`.

First, save your unfinished work:

```bash
git stash push -m "half-done login form"
```

Switch to `main`:

```bash
git switch main
```

Create a branch for the urgent fix:

```bash
git switch -c hotfix/typo
```

Fix the issue, commit it, and complete your work.

Then return to your feature branch:

```bash
git switch feature/login
```

Restore your saved work:

```bash
git stash pop
```

You can now continue working from where you stopped.

---

### Deleting a Stash

If you no longer need a specific stash:

```bash
git stash drop stash@{0}
```

This permanently removes that stash from the list.

---

### Clearing All Stashes

To remove every saved stash:

```bash
git stash clear
```

Be careful with this command because it removes all stashes.

---

### Quick Command Reference

| Command                       | What It Does                                            |
| ----------------------------- | ------------------------------------------------------- |
| `git stash`                   | Temporarily saves current uncommitted changes.          |
| `git stash push -m "message"` | Saves changes with a descriptive label.                 |
| `git stash list`              | Shows all saved stashes.                                |
| `git stash apply`             | Restores the latest stash and keeps it in the list.     |
| `git stash apply stash@{1}`   | Restores a specific stash.                              |
| `git stash pop`               | Restores the latest stash and removes it from the list. |
| `git stash drop stash@{0}`    | Deletes a specific stash.                               |
| `git stash clear`             | Deletes all saved stashes.                              |

---

## 14. Git Tags

Git tags mark important points in your repository history, usually releases.

### Why Tags Exist

Git tags are useful for:

- Marking version releases such as `v1.0.0`
- Bookmarking stable checkpoints
- Referencing a specific commit permanently

Unlike branches, tags do not move when new commits are added.

Example:

```text
A─B─C─D
    ↑   ↑
 v1.0.0 main
````

After adding more commits:

```text
A─B─C─D─E─F
    ↑       ↑
 v1.0.0    main
```

`v1.0.0` stays on commit `C`, while `main` continues moving forward.

---

### Lightweight Tags

A lightweight tag is a simple pointer to a commit.

It does not store extra metadata such as an author, date, or message.

```bash
git tag v1.0.0
```

---

### Annotated Tags

Annotated tags are recommended for releases.

They store additional information such as:

* Author
* Date
* Tag message

Create an annotated tag:

```bash
git tag -a v1.0.0 -m "first stable release"
```

---

### Creating Tags

Tag the current commit:

```bash
git tag v1.0.0
```

Tag a specific commit:

```bash
git tag v0.9.0 a1b2c3d
```

Create an annotated tag with a message:

```bash
git tag -a v1.0.0 -m "release version 1.0.0"
```

---

### Listing Tags

List all tags:

```bash
git tag
```

List tags matching a specific pattern:

```bash
git tag -l "v1.*"
```

View details about a tag:

```bash
git show v1.0.0
```

---

### Pushing Tags to GitHub

Tags are not automatically pushed with normal commits.

Push one specific tag:

```bash
git push origin v1.0.0
```

Push all local tags:

```bash
git push origin --tags
```

---

### Deleting Tags

Delete a tag locally:

```bash
git tag -d v1.0.0
```

Delete the same tag from GitHub:

```bash
git push origin --delete v1.0.0
```

---

### Lightweight vs Annotated Tags

| Type        | Use Case                                                   |
| ----------- | ---------------------------------------------------------- |
| Lightweight | Simple pointer to a commit with no extra metadata          |
| Annotated   | Stores author, date, and message; recommended for releases |

---

## 15. Git Rebase

Git rebase moves your branch commits on top of another branch to create a cleaner and more linear history.

### What is Rebase?

Instead of creating a merge commit, `git rebase` replays your commits on top of the latest commits from another branch.

Suppose your feature branch diverged from `main` at commit `B`.

Your feature branch has commits `C` and `D`, while `main` has moved forward to commit `E`:

```text
      C─D        feature/search
     /
A─B─E            main
````

After running:

```bash
git switch feature/search
git rebase main
```

Git replays your feature commits on top of `E`:

```text
A─B─E─C'─D'
    ↑       ↑
   main   feature/search
```

`C'` and `D'` are new commits containing the same changes as `C` and `D`, but they are now based on the latest `main`.

---

### Rebase vs Merge

A merge keeps the original branch structure and creates a merge commit.

```text
      C─D
     /   \
A─B─E─────M
```

Here, `M` is the merge commit.

A rebase instead replays your work on top of the updated branch:

```text
A─B─E─C'─D'
```

This creates a straight, linear history without an extra merge commit.

---

### Merge vs Rebase

|                         | Merge                      | Rebase             |
| ----------------------- | -------------------------- | ------------------ |
| History                 | Preserves branch structure | Linear and cleaner |
| Merge commit            | Yes                        | No                 |
| Safe on shared branches | Yes                        | No                 |

---

### When to Use Rebase

Rebase is useful:

* Before opening a pull request to keep your branch history clean
* To sync a feature branch with the latest changes from `main`
* On branches that only you are working on

Example:

```bash
# update your feature branch with the latest main

git switch feature/search
git fetch origin
git rebase origin/main
```

This fetches the latest remote changes and replays your feature commits on top of the latest `origin/main`.

---

### Rebasing Before a Pull Request

Before pushing your feature branch for a pull request:

```bash
git switch feature/search
git rebase main
git push --force-with-lease origin feature/search
```

Because rebase rewrites commit history, a normal push may be rejected.

`--force-with-lease` safely updates the remote branch while checking that no unexpected remote changes have been added.

---

### Best Practices

* Rebase branches that only you are working on.
* Rebase your feature branch before opening a pull request if you want a cleaner history.
* Never rebase commits that have already been pushed to a shared branch.
* Remember that rebase creates new versions of your commits.

---

### Abort a Rebase

If the rebase becomes difficult or you want to cancel it:

```bash
git rebase --abort
```

This stops the current rebase and returns your branch to the state it was in before the rebase started.

---

### Important Rule

> ⚠️ Never rebase commits that have already been pushed to a shared branch.

Rebase rewrites commit history, so changing commits that other developers are already using can cause synchronization problems.

---

## 16. Using GitHub to Host Our Repositories

GitHub allows you to host your Git repositories online so you can store your code, maintain its history, share projects, and collaborate with others.

---

### Sign Up on GitHub

To use GitHub, first create a personal GitHub account.

**Step 1:** Go to [github.com/signup](https://github.com/signup).

**Step 2:** Enter your email address or continue using a supported social sign-in option.

**Step 3:** Follow GitHub's prompts to create your account, including choosing your account details such as a username.

**Step 4:** Verify your email address using the verification message sent by GitHub.

**Step 5:** Sign in to your GitHub account.

After completing these steps, your GitHub account is ready to use.

---

### Create a GitHub Repository

A **repository** is where GitHub stores your project's files, code, commits, and version history.

To create one:

**Step 1:** Sign in to GitHub.

**Step 2:** Click the **+** button in the upper-right corner.

**Step 3:** Select **New repository**.

**Step 4:** Choose the repository owner.

**Step 5:** Enter a repository name.

Example:

```text
hello-git
```

**Step 6:** Optionally add a short description of the project.

**Step 7:** Select the repository visibility:

- **Public** → anyone can view the repository.
- **Private** → only you and people you authorize can access it.

**Step 8:** Optionally select **Add a README file**.

**Step 9:** Click **Create repository**.

Your repository is now hosted on GitHub.

---

### Understanding `README.md`

`README.md` is a Markdown file commonly used to document your project in a structured and readable format.

It can explain things such as:

- What the project does
- How to install or run it
- How to use the project
- Project requirements
- Important instructions or documentation

Example:

```markdown
# Hello Git

This is my first Git project.

## Installation

Clone the repository and run the project.
```

GitHub automatically displays the repository's README on the main repository page when one is available.

---

### Cloning a Public Repository

`git clone` downloads a complete copy of a GitHub repository to your local computer.

For a public repository:

```bash
git clone <URL>
```

Example:

```bash
git clone https://github.com/OWNER/REPOSITORY.git
```

Public repositories can normally be cloned without authentication.

---

### Clone a Repository from GitHub Using Git Bash

**Step 1:** Open the repository on GitHub.

**Step 2:** Click the **Code** button above the repository files.

**Step 3:** Select **HTTPS**.

**Step 4:** Copy the repository URL.

It will look similar to:

```text
https://github.com/OWNER/REPOSITORY.git
```

**Step 5:** Open **Git Bash** on your computer.

**Step 6:** Move to the directory where you want to download the project.

Example:

```bash
cd Desktop
```

**Step 7:** Run:

```bash
git clone https://github.com/OWNER/REPOSITORY.git
```

**Step 8:** Git will create a new folder and download the repository files and Git history.

Move inside the cloned repository:

```bash
cd REPOSITORY
```

When a repository is cloned, Git also automatically creates a remote named `origin` that points back to the repository you cloned.

---

### Cloning a Private Repository Using an SSH Key

Private repositories require authentication.

One secure method is to connect GitHub with an **SSH key**.

SSH allows your computer to authenticate with GitHub using a public/private key pair.

---

### Step 1: Check for an Existing SSH Key

Open Git Bash and run:

```bash
ls -al ~/.ssh
```

Look for files such as:

```text
id_ed25519
id_ed25519.pub
```

or:

```text
id_rsa
id_rsa.pub
```

Files ending in `.pub` are public SSH keys.

If you already have a suitable SSH key, you can use it. Otherwise, generate a new one.

---

### Step 2: Generate a New SSH Key

Run:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Replace:

```text
your_email@example.com
```

with the email address associated with your GitHub account.

When Git Bash asks where to save the key:

```text
Enter file in which to save the key:
```

Press **Enter** to accept the default location.

You may also be asked to enter a passphrase.

After generation, you normally have:

```text
~/.ssh/id_ed25519
~/.ssh/id_ed25519.pub
```

The file:

```text
id_ed25519
```

is your **private key** and should never be shared.

The file:

```text
id_ed25519.pub
```

is your **public key** and can be added to GitHub.

---

### Step 3: Add the Key to the SSH Agent

Start the SSH agent:

```bash
eval "$(ssh-agent -s)"
```

Then add your private SSH key:

```bash
ssh-add ~/.ssh/id_ed25519
```

---

### Step 4: Copy Your Public SSH Key

Display the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the complete output.

It normally starts with:

```text
ssh-ed25519
```

---

### Step 5: Add the SSH Key to GitHub

On GitHub:

1. Click your **profile picture**.
2. Open **Settings**.
3. Under **Access**, select **SSH and GPG keys**.
4. Click **New SSH key**.
5. Enter a descriptive title, such as:

```text
Personal Laptop
```

6. Select **Authentication Key** as the key type.
7. Paste your copied public SSH key into the **Key** field.
8. Click **Add SSH key**.
9. Confirm your GitHub account if GitHub asks you to authenticate.

Your computer can now use the SSH key to authenticate with GitHub.

---

### Step 6: Test the SSH Connection

Run:

```bash
ssh -T git@github.com
```

The first time you connect, GitHub may ask you to confirm the host.

After verifying GitHub's fingerprint, type:

```text
yes
```

A successful authentication should identify your GitHub username and confirm that authentication succeeded.

---

### Step 7: Clone the Private Repository with SSH

Open your private repository on GitHub.

Then:

1. Click **Code**.
2. Select **SSH**.
3. Copy the SSH URL.

It will look similar to:

```text
git@github.com:OWNER/REPOSITORY.git
```

Open Git Bash and run:

```bash
git clone git@github.com:OWNER/REPOSITORY.git
```

Git will authenticate using your SSH key and clone the private repository.

---

### Connecting an Existing Local Repository to GitHub

If you already created a project locally using Git, connect it to a GitHub repository with:

```bash
git remote add origin <URL>
```

Example:

```bash
git remote add origin https://github.com/OWNER/REPOSITORY.git
```

This connects your local repository to the GitHub repository and gives that remote the name `origin`.

---

### Viewing Connected Remote Repositories

Use:

```bash
git remote -v
```

Example output:

```text
origin  https://github.com/OWNER/REPOSITORY.git (fetch)
origin  https://github.com/OWNER/REPOSITORY.git (push)
```

This shows the remote URLs Git uses for fetching and pushing.

---

### Understanding `origin`

`origin` is the conventional default nickname Git uses for the remote repository you cloned from.

For example:

```bash
git remote add origin https://github.com/OWNER/REPOSITORY.git
```

Here:

```text
origin
```

is the nickname, while:

```text
https://github.com/OWNER/REPOSITORY.git
```

is the actual remote repository URL.

When you clone a repository with `git clone`, Git normally creates `origin` automatically.

---

### Understanding `main`

`main` is commonly used as the primary branch name for GitHub repositories.

For example:

```bash
git push origin main
```

means:

```text
origin → remote GitHub repository
main   → branch being pushed
```

---

### Rename Your Current Branch

To rename your current branch:

```bash
git branch -M <new_branch_name>
```

For example, rename the current branch to `main`:

```bash
git branch -M main
```

This is commonly used when changing a branch such as `master` to `main`.

---

### Make `main` the Default Branch for New Local Repositories

To tell Git to initialize future local repositories with `main` as the initial branch:

```bash
git config --global init.defaultBranch main
```

After this configuration, running:

```bash
git init
```

will use `main` as the initial branch name for new repositories.

---

### Push Changes to GitHub

To upload the commits from your local `main` branch to GitHub:

```bash
git push origin main
```

Here:

```text
git push → upload local commits
origin   → remote repository
main     → branch being pushed
```

The workflow looks like:

```text
Local Repository
      |
      | git push origin main
      ↓
GitHub Repository
```

---

### Pull Changes from GitHub

Use:

```bash
git pull
```

`git pull` retrieves changes from the remote repository and integrates them into your current local branch.

A typical pull operation can be understood as:

```text
git pull
   ↓
git fetch
   +
integrate remote changes
   ↓
Updated Local Branch
```

For example:

```bash
git pull origin main
```

This retrieves the latest changes from `origin/main` and integrates them into your current branch.

---

### Fetch Changes from GitHub

Use:

```bash
git fetch
```

`git fetch` downloads information about new commits, branches, and other updates from the remote repository without automatically merging those changes into your current local branch.

For example:

```bash
git fetch origin
```

Think of the difference as:

```text
git fetch
Remote → Download updates → Local remote-tracking branches
                              No automatic merge
```

while:

```text
git pull
Remote → Download updates → Integrate into current branch
```

---

### `git pull` vs `git fetch`

| Command | What It Does |
|---|---|
| `git pull` | Downloads remote changes and integrates them into your current branch. |
| `git fetch` | Downloads remote updates without automatically integrating them into your current branch. |

---

### Complete GitHub Hosting Workflow

For an existing local Git repository:

```bash
# connect local repository to GitHub
git remote add origin <URL>

# verify the remote
git remote -v

# rename current branch to main
git branch -M main

# push local commits to GitHub
git push origin main

# retrieve and integrate remote changes
git pull origin main

# retrieve remote updates without integrating them
git fetch origin
```

The basic relationship is:

```text
Local Git Repository
        ↕
   push / pull
        ↕
GitHub Remote Repository
```

---

### Command Reference

| Command | Purpose |
|---|---|
| `git clone <URL>` | Downloads a complete copy of a repository. |
| `git remote add origin <URL>` | Connects a local repository to a remote GitHub repository. |
| `git remote -v` | Shows configured remote repository URLs. |
| `git branch -M main` | Renames the current branch to `main`. |
| `git config --global init.defaultBranch main` | Makes `main` the initial branch name for future local repositories. |
| `git push origin main` | Pushes commits from the local `main` branch to GitHub. |
| `git pull` | Retrieves remote changes and integrates them into the current branch. |
| `git fetch` | Retrieves remote changes without automatically integrating them. |
| `ssh -T git@github.com` | Tests SSH authentication with GitHub. |

---

## 17. GitHub Desktop: GUI for Git and GitHub

GitHub Desktop is a free, open-source graphical user interface (GUI) that lets you work with Git and GitHub without typing Git commands manually.

Using GitHub Desktop, you can:

- Create and clone repositories
- Make commits
- Create and switch branches
- Push changes to GitHub
- Pull changes from GitHub
- Create pull requests
- Work with forks
- Review your Git history visually

---

### Download and Install GitHub Desktop

**Step 1:** Go to [desktop.github.com](https://desktop.github.com/).

**Step 2:** Download GitHub Desktop for your operating system.

For Windows:

1. Click **Download for Windows**.
2. Open the downloaded setup file.
3. Wait for the installation to complete.
4. GitHub Desktop will launch automatically.

For macOS:

1. Download GitHub Desktop for macOS.
2. Open the downloaded file.
3. Extract and open the GitHub Desktop application.
4. Launch GitHub Desktop.

---

### Sign In to GitHub Desktop

After installing GitHub Desktop, connect it to your GitHub account.

On Windows:

1. Open **GitHub Desktop**.
2. Go to **File → Options**.
3. Open the **Accounts** section.
4. Click **Sign Into GitHub.com**.
5. Click **Continue With Browser**.
6. Sign in to your GitHub account in the browser.
7. Complete two-factor authentication if enabled.
8. Allow the browser to return you to GitHub Desktop.

Once authenticated, GitHub Desktop can communicate with repositories on your GitHub account.

---

### Create a Repository in GitHub Desktop

You can create a Git repository directly from GitHub Desktop.

**Step 1:** Open GitHub Desktop.

**Step 2:** Select:

```text
File → New Repository
```

If you have no repositories added yet, you may instead see:

```text
Create a New Repository on your Hard Drive
```

**Step 3:** Enter the repository information.

**Name**

Enter the repository name.

Example:

```text
hello-github-desktop
```

**Description**

Optionally describe what the project does.

Example:

```text
A practice repository for learning GitHub Desktop
```

**Local Path**

Choose where the repository should be stored on your computer.

Example:

```text
Documents/GitHub/
```

GitHub Desktop will create the repository folder inside that location.

**Initialize this repository with a README**

Enable this option if you want GitHub Desktop to automatically create a `README.md` file.

**Git Ignore**

Optionally select a `.gitignore` template depending on the technology you are using.

Examples:

```text
Python
Node
VisualStudio
Unity
```

**License**

Optionally select a software license.

**Step 4:** Click:

```text
Create Repository
```

The repository now exists locally on your computer.

---

### Publish Your Repository on GitHub

Creating a repository in GitHub Desktop does not automatically make it available on GitHub.

You need to **publish** it.

**Step 1:** Open the repository in GitHub Desktop.

**Step 2:** Click:

```text
Publish repository
```

**Step 3:** Review the repository name.

Example:

```text
hello-github-desktop
```

**Step 4:** Add or update the description if required.

**Step 5:** Choose the repository visibility.

GitHub Desktop provides the option:

```text
Keep this code private
```

If selected:

```text
Private Repository
```

If unselected:

```text
Public Repository
```

**Step 6:** If you belong to a GitHub organization, optionally choose the organization where you want to publish the repository.

Otherwise, publish it under your personal GitHub account.

**Step 7:** Click:

```text
Publish Repository
```

Your local repository is now connected to a remote repository on GitHub.

---

### Public vs Private Repositories

A **public repository** can be viewed by anyone on the internet.

You can test this by copying the repository URL and opening it in an incognito or private browser window.

```text
Public Repository
      ↓
Anyone can view it
```

A **private repository** can only be viewed by you and people who have been given access.

```text
Private Repository
      ↓
Authorized users only
```

If someone without permission tries to access a private repository, GitHub generally treats the resource as unavailable and may display:

```text
404
This is not the web page you are looking for.
```

This prevents unauthorized users from confirming the contents of the private repository.

---

### Make Changes and Commit Using GitHub Desktop

Open the project files in your preferred editor and make your changes.

GitHub Desktop automatically detects modified files.

The **Changes** tab will show the files that changed.

Enter a commit message:

```text
add project documentation
```

Then click:

```text
Commit to main
```

After committing, upload the commit to GitHub by clicking:

```text
Push origin
```

The basic workflow becomes:

```text
Edit Files
    ↓
GitHub Desktop Detects Changes
    ↓
Write Commit Message
    ↓
Commit to Branch
    ↓
Push origin
    ↓
GitHub
```

---

### Creating a Branch in GitHub Desktop

Branches allow you to work on a feature or fix without directly changing the stable `main` branch.

**Step 1:** Open your repository in GitHub Desktop.

**Step 2:** At the top of GitHub Desktop, click:

```text
Current Branch
```

**Step 3:** Select the branch that should be the starting point.

Usually:

```text
main
```

**Step 4:** Click:

```text
New Branch
```

**Step 5:** Enter a branch name.

Example:

```text
feature/login
```

or:

```text
feature/search
```

**Step 6:** Confirm that the branch is based on the correct branch.

For example:

```text
Create branch based on: main
```

**Step 7:** Click:

```text
Create Branch
```

GitHub Desktop automatically switches to the newly created branch.

The structure may now look like:

```text
main
  \
   feature/login
```

---

### Publish a Branch to GitHub

A new branch created in GitHub Desktop initially exists only on your computer.

To make it available on GitHub:

**Step 1:** Make sure your new branch is selected.

Example:

```text
feature/login
```

**Step 2:** Click:

```text
Publish branch
```

The branch is now available on GitHub.

---

### Understanding Pull Requests

A **Pull Request (PR)** is a proposal to merge changes from one branch or fork into another branch.

For example:

```text
feature/login
      ↓
Pull Request
      ↓
Review
      ↓
main
```

A pull request lets the repository maintainer review:

- What files changed
- What code was added or removed
- Commit history
- Discussions and comments
- Automated checks
- Possible merge conflicts

A change itself is not automatically a pull request.

A pull request is created when someone **proposes that their branch or fork should be merged into another branch**, usually `main`.

---

### Create a Pull Request Using GitHub Desktop

Suppose you created:

```text
feature/login
```

and now want to merge it into:

```text
main
```

**Step 1:** Make your changes on `feature/login`.

**Step 2:** Review the files in the **Changes** tab.

**Step 3:** Enter a meaningful commit message.

Example:

```text
add login form validation
```

**Step 4:** Click:

```text
Commit to feature/login
```

**Step 5:** Upload your branch using:

```text
Push origin
```

or, if it has never been uploaded before:

```text
Publish branch
```

**Step 6:** GitHub Desktop will provide the option:

```text
Preview Pull Request
```

Click it.

**Step 7:** Confirm the base branch.

For example:

```text
base: main
```

Your current branch will contain the proposed changes:

```text
feature/login → main
```

**Step 8:** Review the differences shown in GitHub Desktop.

**Step 9:** Click:

```text
Create Pull Request
```

GitHub Desktop will open GitHub in your web browser.

**Step 10:** Enter a meaningful pull request title.

Example:

```text
Add login form validation
```

**Step 11:** Add a description explaining the changes.

Example:

```text
This pull request adds validation for empty username and password fields.
```

**Step 12:** Click:

```text
Create pull request
```

Your pull request is now ready for review.

---

### Review and Merge a Pull Request on GitHub

Before merging a pull request, review the proposed changes.

**Step 1:** Open the repository on GitHub.

**Step 2:** Click:

```text
Pull requests
```

**Step 3:** Open the pull request you want to review.

**Step 4:** Review:

```text
Conversation
Commits
Checks
Files changed
```

Pay particular attention to:

```text
Files changed
```

to understand exactly what code will be added or removed.

**Step 5:** Make sure the pull request has no unresolved problems or merge conflicts.

If the repository uses required reviews or automated checks, those requirements must be satisfied before merging.

**Step 6:** When the changes are ready, click:

```text
Merge pull request
```

Depending on the repository configuration, GitHub may also provide:

```text
Squash and merge
Rebase and merge
```

**Step 7:** Confirm the merge by clicking:

```text
Confirm merge
```

The changes are now part of the base branch, such as:

```text
main
```

**Step 8:** Optionally click:

```text
Delete branch
```

if the feature branch is no longer needed.

The complete workflow is:

```text
Create Branch
     ↓
Make Changes
     ↓
Commit
     ↓
Push / Publish Branch
     ↓
Create Pull Request
     ↓
Review Changes
     ↓
Merge Pull Request
     ↓
main Updated
```

---

### What is Forking?

A **fork** creates your own copy of another repository under your GitHub account.

The fork remains connected to the original repository, which GitHub commonly refers to as the **upstream repository**.

Example:

```text
Original Repository
github.com/original-owner/project
              ↓
             Fork
              ↓
Your Repository
github.com/your-username/project
```

A fork allows you to:

- Experiment with someone else's project without changing the original repository
- Maintain your own version of the project
- Create branches and commits independently
- Contribute changes back to the original repository using a pull request

---

### Create a Fork on GitHub

**Step 1:** Open the repository you want to fork.

**Step 2:** Click:

```text
Fork
```

in the upper-right area of the repository page.

**Step 3:** Select the owner for the fork.

Usually this will be your personal GitHub account.

**Step 4:** Keep or change the repository name.

GitHub normally uses the same repository name as the original.

**Step 5:** Optionally add a description.

**Step 6:** Optionally enable:

```text
Copy the DEFAULT branch only
```

For many contribution workflows, copying only the default branch is enough.

**Step 7:** Click:

```text
Create fork
```

GitHub creates the fork under your account.

---

### Clone Your Fork Using GitHub Desktop

After creating the fork, download it to your computer using GitHub Desktop.

**Step 1:** Open your fork on GitHub.

The URL should now contain your username.

Example:

```text
github.com/YOUR-USERNAME/PROJECT
```

**Step 2:** Click:

```text
Code
```

**Step 3:** Select:

```text
Open with GitHub Desktop
```

GitHub Desktop will open automatically.

**Step 4:** Choose the local path where you want to store the repository.

Example:

```text
Documents/GitHub/
```

**Step 5:** Click:

```text
Clone
```

Your fork now exists:

```text
Original Repository
        ↓
       Fork
        ↓
Your GitHub Account
        ↓
      Clone
        ↓
Your Computer
```

You can now create branches and make changes using GitHub Desktop.

---

### Contribute Back Through a Fork

When contributing to a repository where you do not have direct write access, a common workflow is:

```text
Fork Original Repository
        ↓
Clone Your Fork
        ↓
Create Feature Branch
        ↓
Make Meaningful Changes
        ↓
Commit Changes
        ↓
Push Branch
        ↓
Open Pull Request
        ↓
Original Repository Maintainer Reviews It
        ↓
Merge if Approved
```

Your pull request can propose that changes from your fork be merged into the original repository.

---

### Do Not Open Pull Requests Blindly

Do not create pull requests simply to increase activity on your GitHub profile.

Before contributing:

- Understand the repository and its purpose.
- Read `README.md`.
- Check `CONTRIBUTING.md` if available.
- Read existing issues and pull requests.
- Make sure your change is useful.
- Follow the project's contribution guidelines.
- Test your changes before submitting them.
- Write a clear pull request title and description.

Always open a pull request after making **meaningful and relevant changes**.

Unnecessary pull requests can create extra work for repository maintainers.

---

### Understanding GitHub Stars

A GitHub **Star** works similarly to bookmarking or showing appreciation for a repository.

If you find a repository useful or interesting:

**Step 1:** Open the repository on GitHub.

**Step 2:** Click:

```text
Star
```

Starring a repository makes it easier to find later and also shows appreciation for the project.

You can think of it simply as:

```text
Star ≈ Bookmark + Appreciation
```

---

### Practice Workflow with a Friend

A useful way to understand Git and GitHub Desktop is to practice the complete collaboration workflow with a friend.

Create a simple test repository and practice:

```text
Create Repository
      ↓
Publish Repository
      ↓
Clone Repository
      ↓
Create Branches
      ↓
Make Changes
      ↓
Commit Changes
      ↓
Push Changes
      ↓
Pull Changes
      ↓
Create Pull Requests
      ↓
Review Each Other's Code
      ↓
Merge Pull Requests
```

You can also fork each other's sample repositories and practice contributing through forks.

This creates a realistic workflow for understanding GitHub collaboration and helps you become more comfortable working with repositories, branches, commits, reviews, and pull requests.

---

### GitHub Desktop Workflow at a Glance

```text
Repository
    ↓
Create / Clone
    ↓
Create Branch
    ↓
Edit Files
    ↓
Review Changes
    ↓
Commit
    ↓
Push / Publish
    ↓
Pull Request
    ↓
Review
    ↓
Merge into main
```

---

### Quick Reference

| Action | GitHub Desktop / GitHub |
|---|---|
| Create repository | `File → New Repository` |
| Publish local repository | `Publish repository` |
| View changed files | `Changes` |
| Save changes | `Commit to <branch>` |
| Upload commits | `Push origin` |
| Download remote updates | `Fetch origin` / `Pull origin` |
| Create branch | `Current Branch → New Branch` |
| Switch branch | `Current Branch → Select Branch` |
| Upload new branch | `Publish branch` |
| Create pull request | `Preview Pull Request → Create Pull Request` |
| Merge pull request | GitHub → `Merge pull request` |
| Fork repository | GitHub → `Fork` |
| Clone to Desktop | GitHub → `Code → Open with GitHub Desktop` |
| Star repository | GitHub → `Star` |

---

## 18. Using Git in VS Code

VS Code has built-in Git support in the Source Control panel, showing changed files, the staging area,
and a commit box, all without leaving the editor.

---

### Source Control Panel

Open the Source Control panel using:

**Windows / Linux**

```text
Ctrl + Shift + G
```

**macOS**

```text
Cmd + Shift + G
```

The Source Control panel shows:

- Changed files
- Staged changes
- Unstaged changes
- Commit message box
- Repository actions

---

### Staging Changes

Files you modify appear under the **Changes** section.

**1. Stage one file**

Click the `+` icon next to a changed file.

Terminal equivalent:

```bash
git add filename.py
```

**2. Stage all changes**

Click the `+` icon next to **Changes**.

Terminal equivalent:

```bash
git add .
```

**3. Unstage a file**

Under **Staged Changes**, click the `-` icon next to the file.

Every action in the Source Control interface maps to Git commands underneath.

---

### Creating Commits

After staging your changes:

**Step 1:** Type a commit message in the message box at the top of the Source Control panel.

Example:

```text
add user authentication
```

**Step 2:** Click the **Commit** checkmark button.

Terminal equivalent:

```bash
git commit -m "add user authentication"
```

---

### Synchronizing Changes

VS Code can synchronize your local and remote repository using the **Sync Changes** button or circular arrows icon.

Click:

```text
Sync Changes
```

This synchronizes remote and local changes by pulling incoming changes and pushing your outgoing commits.

Terminal equivalent:

```bash
git pull origin main
git push origin main
```

---

### Viewing File Differences

Click any modified file inside the **Source Control** panel.

VS Code opens a diff editor that lets you compare the previous version with your current changes.

Terminal equivalents:

```bash
# view unstaged changes
git diff

# view staged changes
git diff --staged
```

This makes it easier to review exactly what was added, removed, or modified before committing.

---

### Timeline View

VS Code provides a **Timeline** view for examining the history of a file.

To view it:

1. Open the file in VS Code.
2. Open the **Explorer** panel.
3. Find the **Timeline** section for the file.
4. Review its previous commits and changes.

You can also right-click a file and use the available timeline/history options.

Terminal equivalent:

```bash
git log --oneline -- filename.py
```

This displays commits that affected that specific file.

---

### Managing Branches

Your current Git branch appears in the bottom-left area of the VS Code status bar.

Click the branch name to create or switch branches.

#### Create a New Branch

Click the current branch name and select:

```text
Create new branch...
```

Enter a branch name such as:

```text
feature/new-branch
```

Terminal equivalent:

```bash
git switch -c feature/new-branch
```

#### Switch to Another Branch

Click the branch name and select the branch you want.

For example:

```text
main
```

Terminal equivalent:

```bash
git switch main
```

---

### Merge Conflict Resolution

When Git detects a merge conflict, VS Code highlights the conflicting sections directly inside the editor.

A conflict may look like:

```text
<<<<<<< HEAD
your current code
=======
incoming code
>>>>>>> feature/search
```

VS Code provides actions for resolving the conflict.

**Accept Current / Keep Mine**

Keeps the version from your current branch.

```text
Current Version
```

**Accept Incoming / Keep Theirs**

Keeps the incoming version from the branch being merged.

```text
Incoming Version
```

**Accept Both / Keep Both**

Keeps both versions in the file.

```text
Current Version
Incoming Version
```

After resolving the conflict, stage the file and commit the resolution.

```bash
git add filename.py
git commit -m "resolve merge conflict"
```

---

### Publishing a Repository to GitHub

If you have created a local Git repository that is not yet hosted on GitHub, VS Code can publish it directly.

**Step 1:** Open the project in VS Code.

**Step 2:** Open **Source Control**.

```text
Ctrl + Shift + G
```

or on macOS:

```text
Cmd + Shift + G
```

**Step 3:** If required, initialize the repository by clicking:

```text
Initialize Repository
```

**Step 4:** Create and commit your project files.

**Step 5:** Click:

```text
Publish to GitHub
```

**Step 6:** Sign in to GitHub if VS Code asks you to authenticate.

**Step 7:** Choose whether the repository should be:

```text
Public
```

or:

```text
Private
```

**Step 8:** Select the files you want to include.

VS Code then creates the GitHub repository and publishes your local commits.

The equivalent Git workflow includes commands such as:

```bash
git remote add origin https://github.com/username/repo.git
git push -u origin main
```

---

### Git Graph Extension

For a visual representation of branches, commits, and merges, you can install the **Git Graph** extension by mhutchie.

Open Extensions:

```text
Ctrl + Shift + X
```

Then search for:

```text
Git Graph
```

Click:

```text
Install
```

After installation, open the Command Palette:

```text
Ctrl + Shift + P
```

Search for:

```text
Git Graph: View Git Graph
```

Select it to open the visual Git history.

A Git graph helps you visualize:

```text
      C─D
     /   \
A─B─E─────M
```

This makes branch creation, commits, merges, and repository history easier to understand.

---

### VS Code Git Workflow at a Glance

```text
Edit Files
    ↓
Source Control
    ↓
Review Changes
    ↓
Stage (+)
    ↓
Write Commit Message
    ↓
Commit (✓)
    ↓
Sync / Push
    ↓
GitHub
```

---

## 19. Git Scenario 2: Multi-User Setup

**Invite collaborators** via repository Settings, then use **Issues** to track work:

| Field | Purpose |
|---|---|
| Title | Short summary |
| Description | Full details |
| Assignees | Who's responsible |
| Labels | Category (bug, enhancement...) |
| Project / Milestone | Groups issue under bigger goals |
| Development | Links a branch/PR to the issue |

> 💬 Issues work like a social feed — comment, react, and close once resolved.

**Team branch workflow:**
```bash
git checkout -b feature/login       # 1. create & switch to a feature branch
git add .
git commit -m "add login page"      # 2. make changes and commit
git push -u origin feature/login    # 3. push and open a pull request
```

---

## 20. Modern Workflow

- 🤖 **AI-generated commit messages** — many tools (including VS Code) can draft one for you from your diff.
- 🌿 **Branch-per-experiment** — trying 4 different approaches? Make 4 branches, merge only the one that works.

```bash
git switch -c feature/todays-work
git add .
git commit -m "describe each logical step"
git push -u origin feature/todays-work
```

---

## 21. Conclusion

### ✅ Best Practices
- **Present tense commit messages** — `"Fix login bug"`, not `"Fixed login bug"`
- **Meaningful messages** — describe *what* and *why*, not "fixed stuff"
- **Short-lived branches** — merge back to main as soon as it's ready
- **Never push secrets** — no passwords, `.env` files, or API keys (once leaked, rotate them immediately)
- **Always review before committing** — `git status` and `git diff` catch mistakes early

### ⚡ Quick Reference Cheat Sheet

| Command | What it does |
|---|---|
| `git init` | Start a new repository |
| `git clone <url>` | Copy a remote repository |
| `git status` | Check current state |
| `git add .` | Stage all changes |
| `git commit -m "msg"` | Save a snapshot |
| `git log --oneline` | Compact commit history |
| `git branch -a` | List all branches |
| `git switch -c <name>` | Create + switch to a branch |
| `git merge <branch>` | Merge a branch into current |
| `git stash` / `git stash pop` | Park & restore uncommitted work |
| `git push` / `git pull` | Sync with GitHub |
| `git reset --hard HEAD~1` | Undo last commit (⚠️ discards changes) |
| `git revert <commit>` | Safely undo a **pushed** commit |

---

<div align="center">

### 🎉 You now have a complete, practical foundation in Git & GitHub.
**The best way to lock it in: open a terminal right now and try every command above.**

</div>
