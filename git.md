---
title: Git
layout: default
nav_order: 2
---

# Git reference


## Git Command Overview

| Category              | Command                              | Description        |
|-----------------------|--------------------------------------|--------------------|
| **Config**            | `git config --global`                | Configuration      |
| **Repo**              | `git init`                           | New repo           |
|                       | `git clone <url>`                    | Clone remote       |
| **Stage**             | `git status`                         | Check status       |
|                       | `git add <file>`                     | Stage changes      |
| **Commit**            | `git commit -m "msg"`                | Commit             |
| **History**           | `git log --oneline --graph`          | Log                |
|                       | `git diff`                           | Unstaged changes   |
| **Branch**            | `git branch <name>`                  | Create branch      |
|                       | `git checkout <branch>` or `git switch <branch>` | Switch |
| **Merge/Rebase**      | `git merge <branch>`                 | Merge              |
|                       | `git rebase <branch>`                | Rebase             |
| **Remote**            | `git push origin <branch>`           | Push               |
|                       | `git pull`                           | Pull + merge       |
| **Undo**              | `git restore <file>`                 | Discard changes    |
|                       | `git restore --staged <file>`        | Unstage            |
|                       | `git reset --soft HEAD~1`            | Undo commit (keep changes) |
|                       | `git revert <hash>`                  | Safe undo commit   |
| **Stash**             | `git stash` / `git stash pop`        | Temporary save     |

## Staging
```bash
git add -A           # stage all changes (eq: --all)
git add .            # stage current dir and subdirs
git add file.txt     # stage file.txt
git add *.txt        # stages matching files
```

## Status & Unstage
```bash
git status
git reset	# unstage all
```

## Commit
Confirming and saving changes permanently.
```bash
git commit -m "message"
git commit --amend           # edit last commit
git commit -am "message"     # stage all tracked files and commit
```

## Reset
```bash
git reset HEAD~			# undo last commit (keep changes)
git rm
git reset
git reset --hard
git rm -f four.txt
git rm --cached four.txt
git rm -r myFolder
```

## View History
```bash
git log
git log --oneline
```

## Branching
```bash
git branch
git branch development
git checkout development
git checkout main
git checkout development
git merge main -m "merging main to development"
git checkout main
git merge development -m "Merging on main with development"
```

## Merge
```bash
git merge dev	# merge dev into current
```

## Conflict
A conflict happens when both branches changed the same lines. Git stops the merge and marks the file:

```text
<<<<<<< HEAD
your version (current branch)
=======
their version (branch being merged)
>>>>>>> dev
```

```bash
git status                   # lists files with conflicts ("both modified")
# edit each file: keep what you want, delete the <<<<<<< ======= >>>>>>> markers
git add file.txt             # mark the conflict as resolved
git commit                   # finish the merge
git merge --abort            # or: give up and go back to before the merge
```

## Previous Version
```bash
git log --oneline
git checkout commit-hash #previous version
```

## Compare
```bash
git diff 'newest_id' 'oldest_id'
```

## Push 
Sending local changes to the remote.
```bash
git push origin main
git push origin staging
git push origin development
```

## Fetch 
Bringing remote changes into your local repository, but not merging.
```bash
git fetch
git merge
```

## Pull 
Fetching plus merging.
```bash
git pull
```

## Restore
```bash
git restore one.txt
git restore folder
git restore .
git restore --staged .    #restore staged
```

## Stash 
For switching branches, stash your current branch
```bash
git stash
git stash pop  #restores stash
git stash apply
git stash list
git stash pop stash@{0}
git stash apply stash@{0}
git stash drop
```

## Revert
```bash
git revert hash
```
		
## Rebase
```bash
git rebase main
```

## Mac / Global Ignore
```bash
# Globally excluding .DS_Store file, which is used for mac UI
git config --global core.excludesfile ~/.gitignore_global
echo .DS_Store >> ~/.gitignore_global
```

## Initial setup
```bash
# configure git identity
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# create SSH key
ssh-keygen -t ed25519 -C "you@example.com"

# Start the SSH agent and add your key
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Copy public key
cat ~/.ssh/id_ed25519.pub

# Add to github -> Github:Settings:SSH and GPG keys:New SSH key:Paste key.

# Test Connection
ssh -T git@github.com

# Clone repository
git clone git@github.com:USERNAME/REPOSITORY.git

# Checks
git config --global --list
git remote -v
```
