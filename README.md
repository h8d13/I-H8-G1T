# I-H8-G1T

## Basics
> `git init .`
> `git clone <url>`

## Smart alias

`alias suicide="echo 'feat: '$(date +%d%m%Y)'-'$(head /dev/urandom | tr -dc A-Za-z0-9 | head -c 4)"`

### 😄HAPPY:

```
git add .
git commit -m "suicide" 
git push origin master
```
---
### 🫤MAYB:
```
git diff
git log --oneline
git reset --soft HEAD~1 ## Undo last withotu discard changes
git checkout -b new-branch 
git pull --rebase # Pull without request
```
---
### 🧠USEFUL:
```
git commit --amend            # Edit last 
git stash                     # Temporarily save changes without committing
git stash pop                 # Apply and remove 
git branch -D branch-name     # Force delete a branch
git blame file.txt
git log --author="username"   # For more blaming        
```
---
### 😢SAD:
```
git status
git reset --hard HEAD~x         or         git reset --hard origin/master          or    git reset --hard HEAD
git clean -fd
```
---

## Notes:

"Master" might be "main" for you.

```
ssh-keygen -t ed25519
cat id_ed25519.pub then copy its output Go to `Settings > Keys` for access.
eval "$(ssh-agent -s)"
Agent pid 13409
ssh-add ~/.ssh/id_ed25519
```

---

