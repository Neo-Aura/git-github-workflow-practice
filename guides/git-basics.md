# Git Basics — Practical Guide

## 1. Overview

Git is a distributed version control system used to track changes in files and collaborate on projects.

## 2. Configure Git

Set the name and email used for your commits.

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Replace these example values with your own preferred commit identity.

Check your configuration:

```bash
git config --global --list
```

## 3. Initialize a Repository

Create a practice directory and initialize Git:

```bash
mkdir git-basics-lab
cd git-basics-lab
git init
```

## 4. Check Repository Status

Create a file and inspect its status:

```bash
echo "Learning Git" > notes.txt
git status
```

Git reports that `notes.txt` is untracked.

## 5. Stage and Commit Changes

Stage the file:

```bash
git add notes.txt
git status
```

Commit the staged change:

```bash
git commit -m "Add initial learning notes"
```

A commit records a snapshot of staged changes.

## 6. View Commit History

```bash
git log
git log --oneline
```

These commands display repository history in detailed and compact formats.

## 7. Compare Changes

Modify `notes.txt` and inspect the differences:

```bash
echo "Practicing version control" >> notes.txt
git diff
```

`git diff` shows unstaged changes. After staging, use `git diff --staged` to inspect changes prepared for the next commit.

## 8. Practice Tasks

1. Initialize a new local repository.
2. Create two text files.
3. Stage and commit the first file.
4. Make a change to the second file and inspect its status.
5. Stage and commit the second file.
6. View the commit history using `git log --oneline`.
7. Modify a committed file and inspect the output of `git diff`.

## 9. Key Learning

The basic Git workflow is:

**Working directory → Staging area → Repository**

Practice these commands locally before using them in a shared or production repository.
