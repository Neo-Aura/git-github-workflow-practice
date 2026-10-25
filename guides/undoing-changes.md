# Git — Undoing Changes

## 1. Overview

Git provides different commands for undoing changes. Choose the command based on whether changes are unstaged, staged, or already committed.

## 2. git restore

### Discard unstaged changes to a tracked file

```bash
git restore notes.txt
```

This replaces the file's unstaged changes with the version in the index. Those discarded edits may be difficult to recover.

### Unstage a file

```bash
git restore --staged notes.txt
```

This removes the file from the staging area while preserving its working-directory changes.

## 3. git revert

Create a new commit that reverses the changes introduced by an earlier commit.

```bash
git log --oneline
git revert <commit-hash>
```

Replace `<commit-hash>` with the actual commit ID you want to reverse.

`git revert` preserves existing history and is generally appropriate for undoing changes that have already been shared.

## 4. git reset

Move the current branch pointer to an earlier commit.

### Soft reset

```bash
git reset --soft HEAD~1
```

Moves the branch back one commit while keeping the changes staged.

### Mixed reset

```bash
git reset --mixed HEAD~1
```

Moves the branch back one commit and leaves the changes in the working directory, unstaged. This is the default reset mode.

### Hard reset

```bash
git reset --hard HEAD~1
```

Moves the branch back one commit and discards tracked working-directory changes and staged changes that are not retained by the target commit.

**Warning:** `git reset --hard` can permanently discard work. Use it only in a disposable practice repository when you understand the consequences.

## 5. Comparison

| Command | Main purpose |
|---|---|
| `git restore` | Discard or unstage file changes |
| `git revert` | Undo a commit by creating another commit |
| `git reset` | Move a branch pointer to another commit |

## 6. Practice Tasks

Use a disposable local repository:

1. Create and commit a file.
2. Modify it and test `git restore` on an unstaged change.
3. Stage a change and test `git restore --staged`.
4. Create another commit and test `git revert`.
5. Practice `git reset --soft` and `git reset --mixed` on separate test commits.
6. Review the commit history after each operation.

Avoid experimenting with destructive commands in a repository containing work you need.

## 7. Key Learning

Understand the difference between changing files, changing the staging area, and changing commit history before selecting an undo command.
