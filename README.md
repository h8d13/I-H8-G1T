# I-H8-G1T

## Basics
> `git init .`
> `git clone <url>`

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

---
### 😢SAD:

```
git status

git reset --hard <id>
git push --force-with-lease
```
> Can also browse files at different moments by going to commits area and finding where you f*cked it, download zip, then meld to compare to current code.
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

Now for the lazy ones like me: I added to my bashrc then sourced.

```
comsui() {
  # ID + Date + Count
  randid=$(head /dev/urandom | tr -dc A-Za-z0-9 | head -c 6)
  today=$(date "+%m-%d")
  count_file="/tmp/commit_count_$today"
  if [ ! -f "$count_file" ]; then
    echo "1" > "$count_file"
    chmod 644 "$count_file"
  fi
  count=$(cat "$count_file" 2>/dev/null || echo "1")
  # Ensure count is a number
  count=$(($count + 0))
  
  # Create full message
  msg="$randid $(date "+%H:%M") #$(printf "%03d" $count)"
  
  echo "Commit suicide message: \"$msg\""
  git add .
  read -p "Commit and push to origin/master? [y/N] " confirm
  if [[ "$confirm" =~ ^[Yy]$ ]]; then
    if git commit -m "$msg" && git push origin master; then
      # Increment count and write back to file
      count=$((count + 1))
      echo "$count" > "$count_file"
      echo "Count incremented to $count"
    else
      echo "Git operations failed, count not incremented."
    fi
  else
    echo "Aborted."
  fi
}
``` 
