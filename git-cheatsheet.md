# 🔧 Git Cheat Sheet (Interview-Focused)

---

# 🔹 1. Setup & Config

```bash
git config --global user.name "Aravind"
git config --global user.email "you@example.com"
git config --list
```

👉 Done once per machine

---

# 🔹 2. Initialize & Clone

```bash
git init
git clone <repo-url>
```

👉 `init` → new repo
👉 `clone` → existing repo

---

# 🔹 3. Basic Workflow (MOST IMPORTANT)

```bash
git status
git add file.txt
git add .
git commit -m "message"
git push
```

👉 This is your **daily flow**

---

# 🔹 4. Branching (VERY IMPORTANT)

### Create & switch branch

```bash
git checkout -b feature-branch
```

(or modern)

```bash
git switch -c feature-branch
```

---

### Switch branch

```bash
git checkout main
```

---

### List branches

```bash
git branch
```

---

### Delete branch

```bash
git branch -d feature-branch
```

---

# 🔹 5. Pull & Sync

```bash
git pull
git fetch
```

👉 Difference:

* `pull` = fetch + merge
* `fetch` = only download changes

---

# 🔹 6. Merge & Rebase

### Merge

```bash
git merge feature-branch
```

---

### Rebase

```bash
git rebase main
```

👉 Interview tip:
Know difference:

* Merge → keeps history
* Rebase → cleaner linear history

---

# 🔹 7. Undo Changes (VERY IMPORTANT)

### Unstage file

```bash
git reset file.txt
```

---

### Discard changes

```bash
git checkout -- file.txt
```

---

### Undo last commit (keep changes)

```bash
git reset --soft HEAD~1
```

---

### Hard reset (dangerous)

```bash
git reset --hard HEAD~1
```

---

# 🔹 8. Logs & History

```bash
git log
git log --oneline
git diff
```

---

# 🔹 9. Stash (VERY USEFUL)

```bash
git stash
git stash list
git stash apply
git stash pop
```

👉 Use when switching tasks without committing

---

# 🔹 10. Remote Repos

```bash
git remote -v
git remote add origin <url>
git push -u origin main
```

---

# 🔹 11. Tagging

```bash
git tag v1.0
git push origin v1.0
```

👉 Used for releases

---

# 🔹 12. Delete Files from Repo

```bash
git rm file.txt
git commit -m "remove file"
```

---

# 🔥 Most Important Commands (Focus These)

If short on time:

```bash
git clone
git status
git add
git commit
git push
git pull
git branch
git checkout
git merge
git stash
```

---

# 🧠 Real Interview Scenarios (VERY IMPORTANT)

---

## ✅ 1. You made changes but need to switch branch

```bash
git stash
git checkout another-branch
```

---

## ✅ 2. You committed wrong code

```bash
git reset --soft HEAD~1
```

---

## ✅ 3. Resolve merge conflict

Steps:

```bash
git pull
# fix conflict manually
git add .
git commit
```

👉 Be ready to explain conflict markers:

```
<<<<<<< HEAD
=======
>>>>>>> branch
```

---

## ✅ 4. Sync with latest main branch

```bash
git checkout main
git pull
git checkout feature-branch
git merge main
```

(or rebase)

---

# 🧠 Interview-Level Answers (This is key)

Instead of:
❌ “Git is version control”

Say:
✅ “Git is a distributed version control system that helps track changes, collaborate across teams, and manage code versions efficiently”

---
