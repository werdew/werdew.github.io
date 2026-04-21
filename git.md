---     
title: Git Reference | werdew
nav_order: 2
---

# Git reference

Staging:
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
# Confirming and saving changes permanently.
```bash
git commit -m "message"
git commit --amend	#edit last commit
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
```bash
git log --oneline
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
