<div align="center">

# 🚀 Git & GitHub Handbook
### The Complete Beginner's Guide — Master Version Control, Collaborate Better, Code with Confidence

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Beginner Friendly](https://img.shields.io/badge/Level-Beginner%20Friendly-brightgreen?style=for-the-badge)

</div>

---

## 📑 Table of Contents

1. [Introduction](#1-introduction)
2. [What is Git?](#2-what-is-git)
3. [Centralised vs Distributed Version Control Systems](#3-centralised-vs-distributed-version-control-systems)
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
17. [GitHub Desktop](#17-github-desktop)
18. [Using Git in VS Code](#18-using-git-in-vs-code)
19. [Git Scenario 2: Multi-User Setup](#19-git-scenario-2-multi-user-setup)
20. [Modern Workflow](#20-modern-workflow)
21. [Conclusion](#21-conclusion)

---

## 1. Introduction

Welcome to the **Git & GitHub Handbook** — a beginner-friendly, no-fluff guide to version control, written for anyone picking up Git for the very first time.

This repository exists to take you from *"what even is a commit?"* to confidently branching, merging, resolving conflicts, and collaborating with a team on GitHub — using plain language, visual diagrams, and copy-paste-ready commands instead of dense technical jargon.

Whether you're a student, a self-taught developer, or someone brushing up before a new job, this handbook is structured so you can either:
- 📖 Read it top to bottom as a complete course, or
- 🔍 Jump straight to any of the 21 topics in the [Table of Contents](#-table-of-contents) as a quick reference whenever you get stuck.

> 💡 Star ⭐ this repo if you find it useful, and feel free to open a pull request if you spot something worth improving!

---

## 2. What is Git?

In simple words: **Git is a tool that saves a snapshot of your project every time you tell it to**, so you always have a history to look back on. Each saved snapshot is called a **commit**, and together they form a timeline of your entire project.

If you ever break something or want to see how your code looked yesterday, Git lets you jump right back to that point — nothing is ever truly lost.

**Visualizing a simple Git workflow:**

```
 ✏️ Edit files  →  📋 Stage changes  →  💾 Commit  →  ☁️ Push to GitHub
   (working dir)      (git add)         (git commit)      (git push)
```

| Use Git when you want... |
|---|
| 📜 A clear history of changes over time |
| 💾 Safe backup points you can return to |
| 🤝 Easier teamwork on the same project |
| ↩️ To undo mistakes without losing edits |

**Simple workflow:** Edit your files → Save the changes → Commit them → Push to GitHub.

---

## 3. Centralised vs Distributed Version Control Systems

| | **Centralised (CVCS)** | **Distributed (DVCS)** |
|---|---|---|
| Full history | Lives on one server | Lives on every machine |
| Offline work | Limited | Full commits locally |
| Backup | Single point of failure | Many copies exist |
| Examples | SVN, CVS | **Git**, Mercurial |

Git is distributed by design — this is exactly why it became the industry standard for teams of any size, including the Linux kernel project it was built for.

---

## 4. Git vs GitHub

**What is Git?** Git is the version control *tool* itself — free software installed on your computer that tracks changes to your files, creates commits, and manages branches, all locally.

**What is GitHub?** GitHub is a *website* that hosts your Git repositories online, so your code is backed up in the cloud and can be shared with others. It adds collaboration features on top of Git, like pull requests, issues, and code review.

They are **not** the same thing — Git is the engine, GitHub is one of several places you can park it.

| | Git | GitHub |
|---|---|---|
| What it is | Tool | Hosting service |
| Runs on | Your computer | The cloud |
| Needs internet | No (for local work) | Yes (to sync) |
| Stores history | Yes | Yes (as a remote copy) |

**Git repository** = your project folder + hidden `.git` folder holding all history.
**Alternatives to GitHub:** GitLab, Bitbucket, Codeberg — all work with Git underneath.

---

## 5. Installing Git

| Platform | Command / Steps |
|---|---|
| 🪟 Windows | Download from [git-scm.com](https://git-scm.com), or `winget install --id Git.Git -e --source winget` |
| 🍎 macOS | `xcode-select --install` or `brew install git` |
| 🐧 Linux (Debian/Ubuntu) | `sudo apt update && sudo apt install git` |

**Verify it worked:**
```bash
git --version
# git version 2.x.x
```

You can use Git via the **Command Line** (full control), **VS Code** (built-in panel), or **GitHub Desktop** (visual UI) — all three run the same Git commands underneath.

---

## 6. How Git Works

Git moves your changes through **four areas** before they reach GitHub:

```
📁 Working Dir  ──git add──►  📋 Staging Area  ──git commit──►  💾 Local Repo  ──git push──►  ☁️ Remote Repo
```

| Area | What it means |
|---|---|
| **Working Directory** | Your files on disk — edit freely here |
| **Staging Area** | A holding zone for what you want in the next commit |
| **Local Repository** | Where commits are saved permanently on your machine |
| **Remote Repository** | The copy on GitHub |

---

## 7. Hands-on Git

**Basic checks:**
```bash
git --version
git init          # start tracking a folder
git status        # see what's changed
```

**Set your identity (once per machine):**
```bash
git config --global user.name "Your_Name"
git config --global user.email "Your_Email"
```

### 🔑 The BIG 4 Commands
```bash
git init                      # start a repo
git status                    # check current state
git add <filename>            # stage a file (space-separate multiple)
git commit -m "Commit_Message"  # save a snapshot
```

**More everyday commands:**
```bash
git log                   # full history
git log --oneline         # compact history
git add .                 # stage everything
git restore --staged <filename>  # unstage a file
```

---

## 8. Git Scenario 1: Single User Setup

The simplest end-to-end loop for working solo:

```bash
git init
# ...edit files...
git status
git add .
git commit -m "Meaningful message"
# repeat, then anytime:
git log --oneline
```

That's the entire cycle — **edit → stage → commit → review** — no branches or collaborators needed yet.

---

## 9. Ignoring Files

| File | Purpose |
|---|---|
| `.gitignore` | Lists files/folders Git should **never track** (secrets, `node_modules/`, build output, OS junk) |
| `.gitkeep` | A placeholder to make Git track an otherwise-empty folder |

```gitignore
# .gitignore example
.env
__pycache__/
*.pyc
.DS_Store
dist/
```

```bash
# already tracked before adding to .gitignore?
git rm --cached filename
git commit -m "stop tracking filename"
```

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

A branch = an independent line of development. `main` is the default branch.

```
A─B─C   main
     \
      D─E   feature/search
```

```bash
git branch <branchname>      # create
git branch                   # list (check current)
git switch <branchname>      # move onto it
git merge <branchname>       # merge INTO current branch
git branch -d <branchname>   # delete after merging
```

> 🧠 **Stuck in Vim?** Press `Esc`, then type `:wq` and hit Enter to save & quit.

---

## 12. Merge Conflict

```bash
git switch -c <branchname>   # create + switch in one step
git merge <branchname>
```

A **conflict** happens when both branches changed the *same lines*. Git marks it:

```
<<<<<<< HEAD
your version
=======
their version
>>>>>>> feature/search
```

Fix it manually, remove the markers, then:
```bash
git add filename.py
git commit -m "resolve merge conflict"
```

**Stuck? Abort and start over:**
```bash
git merge --abort
```

---

## 13. Stashing in Git

Temporarily park uncommitted work so you can switch tasks:

```bash
git stash                          # save current changes
git stash push -m "wip on login"   # save with a label
git stash list                     # see all stashes
git stash pop                      # restore + remove from list
git stash apply                    # restore + keep in list
```

> 💡 If `git log --oneline` opens a scrollable pager, press `q` to exit.

---

## 14. Git Tags

Tags mark a **fixed point** in history — usually a release. Unlike branches, they don't move.

```bash
git tag v1.0.0                              # lightweight tag
git tag -a v1.0.0 -m "first stable release" # annotated tag (recommended)
git push origin v1.0.0                      # push a tag
git push origin --tags                      # push all tags
```

| Type | Use case |
|---|---|
| Lightweight | Quick pointer, no metadata |
| Annotated | Stores author, date, message — best for releases |

---

## 15. Git Rebase

Rebase replays your commits on top of another branch, avoiding an extra merge commit and keeping history **linear**.

```
Before:  A─B─E (main)     A─B─E─C'─D' (feature, after rebase)
              \  C─D (feature)
```

```bash
git switch feature/search
git rebase main
```

| | Merge | Rebase |
|---|---|---|
| History | Preserves branch structure | Linear, cleaner |
| Merge commit | Yes | No |
| Safe on shared branches | ✅ Yes | ⚠️ No |

> ⚠️ Only rebase branches **you alone** work on — never rebase commits already pushed and shared.

---

## 16. Using GitHub to Host Our Repositories

1. Sign up at [github.com](https://github.com).
2. Create a repository (with an optional **README.md** — GitHub's "front door" for your project).

```bash
git clone <URL>                        # download a repo (public: easy; private: needs SSH key)
git remote add origin <URL>            # connect local repo to GitHub
git remote -v                          # see connected remotes
git branch -M main                     # rename branch to main
git config --global init.defaultBranch main  # set default for all new repos
git push origin main                   # upload your commits
git pull                               # download + merge remote changes
git fetch                              # download without merging
```

- **origin** → the default nickname for your remote URL
- **main** → the default primary branch name

---

## 17. GitHub Desktop

A free **GUI for Git and GitHub** — clone, commit, branch, push, and pull with buttons instead of commands.

- 🌐 Public repos are viewable by anyone, even in incognito. Private repos show a 404 to outsiders.
- **Pull Request (PR):** a request to merge someone's proposed changes into your project.
- **Forking:** create your own copy of someone else's repo to freely edit, then open a PR back to contribute.
- ⭐ **Starring** = GitHub's "like" button.

> 🎯 **Pro tip:** Practice with a friend — create a sandbox repo, push/pull, branch, and open PRs on each other's code.

---

## 18. Using Git in VS Code

- `Ctrl+Shift+G` (Win/Linux) or `Cmd+Shift+G` (Mac) opens the **Source Control** panel.
- Click `+` to stage a file, `-` to unstage, type a message, and hit ✓ to commit.
- Click the sync icon to pull + push in one step.

**Recommended extension — Git Graph:**
```
Extensions → search "Git Graph" → Install
Ctrl+Shift+P → "Git Graph: View Git Graph"
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
