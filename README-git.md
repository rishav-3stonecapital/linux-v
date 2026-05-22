## Keeping your branch up to date with newer tags

If you started your branch from an older tag (e.g., v6.17) and want to include changes from a newer tag (e.g., v6.20), you have two main options:

### Option 1: Merge the newer tag into your branch
```
git checkout my-feature
git merge v6.20
```
This keeps your branch history and adds a merge commit.

### Option 2: Rebase your branch onto the newer tag
```
git checkout my-feature
git rebase v6.20
```
This rewrites your branch history as if your changes were made on top of v6.20.

**Note:** If there are conflicts, Git will prompt you to resolve them during merge or rebase.

---
# Git Commands Cheat Sheet for linux-v

## 1. Clone your fork
```
git clone https://github.com/<your-username>/linux-v.git
```

## 2. Add upstream remote
git remote add upstream https://github.com/original-owner/linux-v.git
```

```
git remote add upstream https://github.com/original-owner/linux-v.git
```

### Steps to add upstream remote
1. Check your current remotes:
	```
	git remote -v
	```
2. Add the official Linux repository as upstream (if not already added):
	```
	git remote add upstream https://github.com/torvalds/linux.git
	```
3. Verify remotes:
	```
	git remote -v
	```
4. Fetch all branches and tags from upstream:
	```
	git fetch upstream --tags
	```

## 3. Create a new branch
```
git checkout -b <branch-name>
```

## 3a. Tag related commands

### List all tags
```
git tag
```

### Checkout a specific tag (e.g., v6.17)
```
git checkout v6.17
```

### Create a branch from a tag
```
git checkout -b my-feature v6.17
```

---

**Note:**
Tags in Git are just pointers to specific commits (often used for releases) and do not create separate branches. If you want to make changes starting from a tag, create a new branch from that tag:

```
git checkout -b my-feature <tag-name>
```

Replace `<tag-name>` with the tag you want to use (e.g., v6.17). This will create a branch starting from the commit the tag points to, allowing you to make changes and commit as usual.

## 4. Stage and commit changes
```
git add <file1> <file2>
git commit -m "Describe your changes"
```

## 5. Push your branch to your fork
```
git push origin <branch-name>
```

## 6. Fetch and rebase from upstream
```
git fetch upstream
git rebase upstream/main
```

## 7. Open a pull request
- Go to your fork on GitHub and click "Compare & pull request".

---

Replace `<your-username>` and `<branch-name>` as needed.
