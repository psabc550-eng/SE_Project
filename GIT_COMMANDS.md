# GIT COMMANDS – SOFTWARE ENGINEERING LAB

## 1. Git Configuration

**Purpose:** Configure Git and check its settings.

```bash
# Check Git version
git --version

# Set username
git config --global user.name "Your Name"

# Set email
git config --global user.email "you@example.com"

# View Git configuration
git config --list
```

## 2. Create a Local Repository

**Purpose:** Create a new Git repository and save files.

```bash
# Create project directory
mkdir SE_Project

# Enter project directory
cd SE_Project

# Initialize Git repository
git init

# Check repository status
git status

# Add all files to staging area
git add .

# Commit changes
git commit -m "Initial commit"
```

## 3. Clone a Repository

**Purpose:** Download an existing remote repository to your computer.

```bash
# Clone repository
git clone https://github.com/username/SE_Project.git

# Enter cloned repository
cd SE_Project
```

## 4. Git Remote Commands

**Purpose:** Connect and manage remote repositories.

```bash
# Display connected remote repositories
git remote -v

# Add a remote repository
git remote add origin https://github.com/username/SE_Project.git

# Display remote repository details
git remote show origin

# Fetch changes without merging
git fetch origin

# Download and merge changes
git pull origin main

# Push local commits to GitHub
git push origin main

# Rename remote
git remote rename origin upstream

# Rename it back
git remote rename upstream origin

# Change remote URL
git remote set-url origin https://github.com/username/SE_Project.git

# Remove remote
git remote remove origin

# Add remote again
git remote add origin https://github.com/username/SE_Project.git

# Display remote branches
git branch -r

# Fetch all remote branches
git fetch --all
```

## 5. Git Add, Commit and Status

**Purpose:** Track files and save changes.

```bash
# Check status
git status

# Add a particular file
git add frontend/index.html

# Add all files
git add .

# Commit changes
git commit -m "Updated project"

# View changes before staging
git diff

# View staged changes
git diff --staged
```

## 6. Git Branch Commands

**Purpose:** Create and manage different branches.

```bash
# Display local branches
git branch

# Display all local and remote branches
git branch -a

# Display remote branches
git branch -r

# Create a branch
git branch feature

# Switch to an existing branch
git switch feature

# Create and switch to a new branch
git switch -c feature2

# Switch to main
git switch main

# Alternative command to switch branches
git checkout main

# Create and switch using checkout
git checkout -b feature3

# Delete a merged branch
git branch -d feature

# Force delete an unmerged branch
git branch -D feature2

# Check merged branches
git branch --merged

# Delete multiple branches
git branch -d feature-a feature-b feature-c
```

## 7. Git Branching, Merging and Pushing

**Purpose:** Create a feature branch, make changes, merge it into main and push to GitHub.

```bash
# Create and switch to feature branch
git switch -c feature

# Make changes to a file
echo "Feature added" >> frontend/index.html

# Check changes
git status

# Stage changes
git add .

# Commit changes
git commit -m "Added new feature"

# Push feature branch to GitHub
git push -u origin feature

# Switch to main
git switch main

# Merge feature branch into main
git merge feature

# Push updated main branch
git push origin main

# Delete local feature branch
git branch -d feature
```

## 8. Git Push and Upstream Commands

**Purpose:** Upload branches and configure tracking relationships.

```bash
# Push a new branch and set upstream
git push --set-upstream origin feature

# Push changes to main
git push origin main

# Push changes to current upstream branch
git push

# Delete a remote branch
git push origin --delete feature

# Remove references to deleted remote branches
git remote prune origin
```

## 9. Git Switch and Checkout

**Purpose:** Move between branches or restore files.

```bash
# Switch to main
git switch main

# Switch to feature branch
git switch feature

# Create and switch to a branch
git switch -c new-feature

# Checkout an existing branch
git checkout main

# Create and checkout a branch
git checkout -b new-feature

# Restore a file using checkout
git checkout -- frontend/index.html
```

## 10. Undo Changes Using Git Restore

**Purpose:** Undo file modifications and remove files from staging.

```bash
# Undo changes made before staging
git restore frontend/index.html

# Remove a file from staging but keep modifications
git restore --staged frontend/index.html

# Restore all unstaged file changes
git restore .
```

## 11. Git Reset and Revert

**Purpose:** Undo commits and changes.

```bash
# Unstage a particular file
git reset frontend/index.html

# Unstage all files
git reset

# Undo latest commit but keep changes staged
git reset --soft HEAD~1

# Undo latest commit and keep changes unstaged
git reset --mixed HEAD~1

# Completely remove latest commit and its changes
git reset --hard HEAD~1

# Safely undo a commit by creating a new commit
git revert HEAD
```

## 12. Modify the Latest Commit

**Purpose:** Correct the most recent commit message.

```bash
# Change latest commit message
git commit --amend -m "Corrected commit message"

# Example
git commit --amend -m "Updated Login Page"
```

## 13. View Git History

**Purpose:** Display commit history and changes.

```bash
# Display complete commit history
git log

# Display short commit history
git log --oneline

# Display details of latest commit
git show

# Display details of a specific commit
git show <commit-hash>

# View file differences
git diff

# View staged differences
git diff --staged

# View history of HEAD
git reflog
```

## 14. Recover a Deleted Branch

**Purpose:** Restore a branch that was accidentally deleted.

```bash
# Display previous HEAD positions
git reflog

# Recreate deleted branch using commit hash
git branch feature-ui <commit-hash>

# Switch to recovered branch
git switch feature-ui
```

## 15. Git Stash

**Purpose:** Temporarily save uncommitted changes.

```bash
# Save current changes
git stash

# Display saved stashes
git stash list

# Switch to another branch
git switch main

# Apply latest stash but keep it saved
git stash apply

# Apply latest stash and remove it from stash list
git stash pop

# Delete a particular stash
git stash drop

# Delete all stashes
git stash clear
```

## 16. Resolve Merge Conflicts

**Purpose:** Resolve conflicts when two branches modify the same file.

```bash
# Switch to main
git switch main

# Merge feature branch
git merge feature

# Open the conflicted file and manually resolve it
# Remove conflict markers:
# <<<<<<< HEAD
# =======
# >>>>>>> feature

# Stage resolved file
git add frontend/index.html

# Complete merge
git commit -m "Resolved merge conflict"

# Push changes
git push origin main
```

## 17. Create a .gitignore File

**Purpose:** Prevent Git from tracking unnecessary files.

```bash
# Create .gitignore
touch .gitignore
```

Add the following patterns inside `.gitignore`:

```gitignore
# Ignore all log files
*.log

# Ignore node_modules folder
node_modules/

# Ignore a particular file
secret_file.txt

# Ignore temporary folder
temp/

# Ignore backup files
*.bak

# Ignore all files except important_file.txt
folder/*
!folder/important_file.txt
```

Save and push:

```bash
git add .gitignore
git commit -m "Added gitignore"
git push origin main
```

## 18. Git Blame

**Purpose:** Find who modified a particular line or file.

```bash
# Show who modified each line
git blame frontend/index.html

# Show who modified line 25
git blame -L 25,25 frontend/index.html

# Show who modified lines 10 to 20
git blame -L 10,20 frontend/index.html
```

## 19. Create and Apply Patches

**Purpose:** Share code changes between developers using patch files.

### Method 1: Using git format-patch

```bash
# Make changes to a file
# Stage changes
git add .

# Commit changes
git commit -m "Updated CSS"

# Generate patch from latest commit
git format-patch -1 HEAD

# Apply patch
git am < 0001-Updated-CSS.patch

# Push changes
git push origin main
```

### Method 2: Using git diff

```bash
# Generate patch from latest commit
git diff HEAD~1 HEAD > changes.patch

# Apply patch
git apply changes.patch

# Check status
git status

# Stage and commit changes
git add .
git commit -m "Applied patch"

# Push changes
git push origin main
```

## 20. Remove Sensitive Files from Git History

**Purpose:** Remove a sensitive file, such as an API key, from repository history.

```bash
# Remove file from Git history
git filter-repo --path api-key.txt --invert-paths

# Force push rewritten history
git push --force origin main
```

**Note:** This rewrites Git history. Coordinate with collaborators and rotate exposed credentials. `git-filter-repo` may need to be installed separately.

## 21. Handle Push Rejection

**Purpose:** Resolve non-fast-forward errors when remote changes exist.

```bash
# Fetch and rebase remote changes
git pull --rebase origin main

# Push local changes
git push origin main
```

## 22. Update a Feature Branch with Main

**Purpose:** Bring the latest main branch changes into a feature branch.

```bash
# Switch to main
git switch main

# Pull latest changes
git pull origin main

# Switch to feature branch
git switch feature

# Merge main into feature
git merge main

# Push feature branch
git push origin feature
```

## 23. Save Local Changes Before Pulling

**Purpose:** Temporarily save local changes before integrating remote changes.

```bash
# Save local modifications
git stash

# Pull remote changes using rebase
git pull --rebase origin main

# Restore saved modifications
git stash pop

# Push changes
git push origin main
```

## 24. Delete Remote Branch

**Purpose:** Remove a branch from GitHub.

```bash
git push origin --delete feature
```

## 25. Final Git Workflow

**Purpose:** Common sequence used while working on a project.

```bash
# Initialize repository
git init

# Configure username and email
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Add remote repository
git remote add origin https://github.com/username/SE_Project.git

# Rename branch to main
git branch -M main

# Add all files
git add .

# Commit files
git commit -m "Initial commit"

# Push to GitHub
git push -u origin main

# Create a feature branch
git switch -c feature

# Make changes and commit
git add .
git commit -m "Added feature"

# Push feature branch
git push -u origin feature

# Switch to main and merge
git switch main
git merge feature

# Push updated main
git push origin main

# Delete merged feature branch
git branch -d feature
```

---

# IMPORTANT COMMANDS FOR PRACTICAL EXAM

| Requirement | Command |
|---|---|
| Initialize repository | `git init` |
| Clone repository | `git clone URL` |
| Check status | `git status` |
| Add files | `git add .` |
| Commit files | `git commit -m "message"` |
| Push files | `git push origin main` |
| Pull changes | `git pull origin main` |
| Fetch changes | `git fetch origin` |
| Create branch | `git branch branch-name` |
| Switch branch | `git switch branch-name` |
| Create and switch | `git switch -c branch-name` |
| Merge branches | `git merge branch-name` |
| Delete branch | `git branch -d branch-name` |
| Undo file changes | `git restore filename` |
| Undo commit safely | `git revert HEAD` |
| Save temporary changes | `git stash` |
| Restore temporary changes | `git stash pop` |
| View commit history | `git log --oneline` |
| View line history | `git blame filename` |
| Ignore files | `.gitignore` |
| Resolve push rejection | `git pull --rebase origin main` |
| Delete remote branch | `git push origin --delete branch-name` |
