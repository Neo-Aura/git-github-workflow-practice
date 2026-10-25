# Git .gitignore Guide

## 1. What Is .gitignore?

A `.gitignore` file tells Git which untracked files and directories to ignore. It helps prevent temporary files, local configuration, and generated files from being added accidentally.

Important: `.gitignore` does not automatically stop tracking files that Git already tracks.

## 2. Create a .gitignore File

In your local practice repository:

```bash
touch .gitignore
```

Open `.gitignore` in your text editor and add patterns such as:

```gitignore
# Log files
*.log

# Temporary files
*.tmp

# Environment variables and local secrets
.env
.env.*

# Dependency directories
node_modules/

# Build output
dist/
build/
```

These are common examples. Adjust patterns to suit the project you're working on.

## 3. Test the Rules

Create a test file:

```bash
touch debug.log
git status --short
```

If `*.log` is in `.gitignore` and `debug.log` is untracked, it should not appear in the normal untracked-file listing.

Check whether a pattern matches a file:

```bash
git check-ignore -v debug.log
```

## 4. Common Mistakes

- `.gitignore` does not remove files already tracked by Git.
- Ignore patterns are relative to the directory containing the `.gitignore` file, subject to Git's pattern rules.
- Never commit passwords, access tokens, or private keys.
- Review `git status` before staging and committing changes.

## 5. Practice Tasks

1. Create a `.gitignore` file.
2. Add the `*.log` pattern.
3. Create an untracked log file.
4. Use `git check-ignore -v` to verify the matching rule.
5. Add a README and `.gitignore` to your practice repository.
6. Confirm that expected files are tracked and ignored files are excluded.

## 6. Key Learning

Use `.gitignore` to prevent unwanted untracked files from entering version control. Always check the repository status before committing.
