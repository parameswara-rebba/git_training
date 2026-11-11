# 1. Basics

## One-time setup

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --list
```

## Starting a repository

```bash
git init                # turn the current folder into a repository
git clone <url>         # copy an existing repository
```

## The three areas

| Area | What it is | Command that moves work into it |
|---|---|---|
| Working directory | Files as they are on disk | (edit files) |
| Staging area (index) | Changes selected for the next commit | `git add` |
| Repository | Committed history | `git commit` |

## Everyday commands

```bash
git status                    # what changed, what is staged
git add file.txt              # stage one file
git add .                     # stage everything in the current folder
git commit -m "Add file"      # commit what is staged
git commit -am "Fix typo"     # stage tracked files and commit in one step
git diff                      # unstaged changes
git diff --staged             # staged changes
```

## Viewing history

```bash
git log                       # full history
git log --oneline --graph --all
git log -p file.txt           # history of one file with diffs
git show <commit>             # one commit in detail
git blame file.txt            # who last changed each line
```

## Ignoring files

Create a `.gitignore` file in the repository root:

```gitignore
*.log
node_modules/
.env
```

A file that is already tracked keeps being tracked; stop tracking it with
`git rm --cached <file>`.
