# Git Branching and Merging

## 1. Overview

Git branches allow developers to work on changes independently without modifying the main branch until the changes are ready.

## 2. Check Existing Branches

```bash
git branch
```

This lists local branches. The current branch is marked with an asterisk.

## 3. Create and Switch to a Branch

```bash
git switch -c feature/update-notes
```

This creates a new branch and switches to it.

Check the current branch:

```bash
git branch --show-current
```

## 4. Make and Commit a Change

Create a practice file:

```bash
echo "Testing a feature branch" > feature-notes.txt
git add feature-notes.txt
git commit -m "Add feature branch notes"
```

## 5. Switch Back to Main

```bash
git switch main
```

If your local repository uses a different default branch name, use that name instead.

## 6. Merge a Branch

Merge the feature branch into `main`:

```bash
git merge feature/update-notes
```

A merge incorporates changes from another branch into the current branch. Run this command while on the branch that should receive the changes.

## 7. View Branch History

```bash
git log --oneline --graph --all
```

This displays a compact graphical view of commit history across branches.

## 8. Delete a Merged Branch

After confirming that the changes are merged and no longer needed:

```bash
git branch -d feature/update-notes
```

## 9. Practice Tasks

1. Create a local practice repository.
2. Create a feature branch.
3. Add a file and commit the change on that branch.
4. Switch back to the main branch.
5. Merge the feature branch.
6. Inspect the commit history.
7. Delete the merged feature branch.

## 10. Key Learning

Branches help isolate work, while merging brings completed changes together. Practice these commands in a test repository before using them in collaborative projects.
