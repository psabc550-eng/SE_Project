
# GIT BRANCHING AND MERGING COMMANDS

## 1. Branch Management

# Display current branch
git branch

# Purpose: Displays all local branches.
git branch

# Purpose: Displays all local and remote branches.
git branch -a

# Purpose: Creates a new branch.
git branch feature

# Purpose: Switches to an existing branch.
git switch feature

# Purpose: Creates a branch and switches to it.
git switch -c feature2

# Purpose: Switches back to main branch.
git switch main


## 2. Making Changes in a Branch

# Purpose: Switch to feature branch.
git switch feature

# Purpose: Add content to a file.
echo "Feature added" >> frontend/index.html

# Purpose: Check modified files.
git status

# Purpose: Stage all changes.
git add .

# Purpose: Commit changes.
git commit -m "Added new feature"

# Purpose: Push feature branch to GitHub.
git push -u origin feature


## 3. Merging Branches

# Purpose: Switch to main branch.
git switch main

# Purpose: Merge feature branch into main.
git merge feature

# Purpose: Push merged changes to GitHub.
git push origin main


## 4. Deleting Branches

# Purpose: Safely delete a merged branch.
git branch -d feature

# Purpose: Force delete an unmerged branch.
git branch -D feature2

# Purpose: Display remaining branches.
git branch


## 5. Remote Branch Management

# Purpose: Display remote branches.
git branch -r

# Purpose: Fetch a specific remote branch.
git fetch origin feature

# Purpose: Remove deleted remote branch references.
git remote prune origin

# Purpose: Push and set upstream branch.
git push --set-upstream origin feature


## 6. Rebasing

# Purpose: Download latest remote changes.
git fetch origin

# Purpose: Reapply local commits on top of remote main.
git rebase origin/main


## 7. Other Useful Commands

# Purpose: Display commit history.
git log --oneline

# Purpose: Check repository status.
git status

# Purpose: Display file differences.
git diff

# Purpose: Display all remotes.
git remote -v
