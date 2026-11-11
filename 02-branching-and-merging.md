# 2. Branching and merging

A branch is a movable pointer to a commit. `HEAD` points at the branch you are on.

## Branches

```bash
git branch                    # list local branches
git branch -a                 # include remote-tracking branches
git switch -c feature/login   # create a branch and switch to it
git switch main               # switch to an existing branch
git branch -d feature/login   # delete a merged branch
git branch -D feature/login   # delete even if unmerged
```

`git checkout <branch>` and `git checkout -b <branch>` are the older equivalents
of `git switch`.

## Merging

```bash
git switch main
git merge feature/login
```

- **Fast-forward**: `main` has no new commits, so its pointer simply moves forward.
- **Merge commit**: both branches have new commits, so Git creates a commit with two parents.
  Force one with `git merge --no-ff`.

## Resolving conflicts

When both branches change the same lines, Git stops and marks the file:

```text
<<<<<<< HEAD
line from the current branch
=======
line from the branch being merged
>>>>>>> feature/login
```

1. Edit the file to the version you want and remove the markers.
2. `git add <file>`
3. `git commit` (or `git merge --abort` to give up and go back).

## Rebasing

```bash
git switch feature/login
git rebase main               # replay this branch's commits on top of main
```

Rebase gives a linear history but rewrites commits. Do not rebase commits that
other people have already pulled.

## Tags

```bash
git tag v1.0.0                        # lightweight tag
git tag -a v1.0.0 -m "First release"  # annotated tag
git push origin v1.0.0
```
