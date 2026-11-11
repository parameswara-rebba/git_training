# 3. Remotes

A remote is another copy of the repository, usually on GitHub. The default name is `origin`.

## Inspecting and adding

```bash
git remote -v
git remote add origin https://github.com/<user>/<repo>.git
git remote set-url origin <new-url>
```

## Getting changes

```bash
git fetch origin              # download new commits, change nothing locally
git pull origin main          # fetch, then merge into the current branch
git pull --rebase origin main # fetch, then rebase local commits on top
```

`git pull` = `git fetch` + `git merge`.

## Sending changes

```bash
git push -u origin main       # first push: also sets the upstream branch
git push                      # later pushes
git push origin --delete old-branch
```

If the push is rejected because the remote has new commits, pull first, then push again.
Avoid `git push --force` on shared branches; if a force is really needed, use
`git push --force-with-lease`.

## Pull request workflow

1. `git switch -c feature/my-change`
2. Commit the work.
3. `git push -u origin feature/my-change`
4. Open a pull request on GitHub and get it reviewed.
5. Merge, then delete the branch.
6. `git switch main && git pull`

## Forks

```bash
git remote add upstream https://github.com/<original-owner>/<repo>.git
git fetch upstream
git merge upstream/main       # bring your fork up to date
```
