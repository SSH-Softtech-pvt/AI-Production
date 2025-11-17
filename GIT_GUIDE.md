# Git Push Guide - Step by Step Tutorial

## Overview
This guide will teach you how to push your code to a GitHub/GitLab/Bitbucket repository.

## Prerequisites
1. Git installed (✅ you have it)
2. A GitHub/GitLab/Bitbucket account
3. A repository created on the platform (we'll guide you through this)

---

## Step 1: Create a Repository on GitHub

### Option A: Using GitHub Website
1. Go to https://github.com
2. Click the **"+"** icon in the top right → **"New repository"**
3. Repository name: `bio-sanjeevni` (or any name you prefer)
4. Description: "AI Platform for Bio Sanjeevni"
5. Choose **Public** or **Private**
6. **DO NOT** initialize with README, .gitignore, or license (we already have these)
7. Click **"Create repository"**

### Option B: Using GitHub CLI (if installed)
```bash
gh repo create bio-sanjeevni --public --source=. --remote=origin --push
```

---

## Step 2: Add All Files to Git

```bash
# Stage all files (adds them to git's tracking)
git add .

# Check what will be committed
git status
```

**What this does:**
- `git add .` - Stages all files in the current directory
- `git status` - Shows you what files are ready to be committed

---

## Step 3: Commit Your Files

```bash
# Create your first commit with a message
git commit -m "Initial commit: Add comprehensive AI platform folder structure"

# Or for more detailed message:
git commit -m "Initial commit: Add comprehensive AI platform folder structure

- Add complete folder structure for frontend, backend, ML, RAG
- Add environment configuration templates
- Add .gitignore and README
- Add .env.example template"
```

**What this does:**
- `git commit` - Saves a snapshot of your files
- `-m "message"` - Adds a descriptive message about what changed

---

## Step 4: Connect to Remote Repository

### If you created the repo on GitHub:

```bash
# Replace YOUR_USERNAME with your GitHub username
# Replace REPO_NAME with your repository name
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git

# Example:
# git remote add origin https://github.com/arpitsrivastav/bio-sanjeevni.git
```

**What this does:**
- `git remote add origin` - Links your local repo to the remote GitHub repo
- `origin` - Standard name for the main remote repository

### Verify the remote was added:
```bash
git remote -v
```

---

## Step 5: Push to GitHub

```bash
# Push to main branch (first time)
git push -u origin main

# For future pushes, you can just use:
# git push
```

**What this does:**
- `git push` - Uploads your commits to GitHub
- `-u origin main` - Sets up tracking so future pushes are easier
- `origin` - The remote repository
- `main` - The branch name

---

## Step 6: Verify on GitHub

1. Go to your repository on GitHub
2. You should see all your files and folders
3. The README.md will be displayed on the repository homepage

---

## Common Commands Reference

### Daily Workflow:
```bash
# 1. Check what changed
git status

# 2. Add files you want to commit
git add .                    # Add all files
git add specific-file.txt    # Add specific file

# 3. Commit with message
git commit -m "Your message here"

# 4. Push to GitHub
git push
```

### Useful Commands:
```bash
# See commit history
git log

# See what files changed
git diff

# Pull latest changes from GitHub
git pull

# Create a new branch
git checkout -b feature-name

# Switch branches
git checkout main
```

---

## Troubleshooting

### If you get "remote origin already exists":
```bash
# Remove existing remote
git remote remove origin

# Add it again with correct URL
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
```

### If you get authentication errors:
- Use **Personal Access Token** instead of password
- GitHub Settings → Developer settings → Personal access tokens → Generate new token
- Use token as password when prompted

### If you want to use SSH instead of HTTPS:
```bash
# Generate SSH key (if you don't have one)
ssh-keygen -t ed25519 -C "your_email@example.com"

# Add SSH key to GitHub (copy public key)
cat ~/.ssh/id_ed25519.pub

# Use SSH URL instead
git remote set-url origin git@github.com:YOUR_USERNAME/REPO_NAME.git
```

---

## Next Steps After First Push

1. **Protect main branch** (GitHub Settings → Branches)
2. **Set up branch protection rules**
3. **Add collaborators** (Settings → Collaborators)
4. **Set up CI/CD** (use files in `devops/ci/` folder)
5. **Create issues and project board** for task tracking

---

## Quick Start (Copy-Paste Ready)

```bash
# 1. Add all files
git add .

# 2. Commit
git commit -m "Initial commit: Add comprehensive AI platform folder structure"

# 3. Add remote (REPLACE with your actual repo URL)
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git

# 4. Push
git push -u origin main
```

---

**Need help?** Check the error message and refer to the troubleshooting section above!

