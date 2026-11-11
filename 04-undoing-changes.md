# 4. Undoing changes

| Situation | Command |
|---|---|
| Discard unstaged changes to a file | `git restore file.txt` |
| Unstage a file, keep the changes | `git restore --staged file.txt` |
| Fix the last commit message | `git commit --amend -m "Better message"` |
| Add a forgotten file to the last commit | `git add file && git commit --amend --no-edit` |
| Undo the last commit, keep changes staged | `git reset --soft HEAD~1` |
| Undo the last commit, keep changes unstaged | `git reset HEAD~1` |
| Undo the last commit and throw the changes away | `git reset --hard HEAD~1` |
| Undo a commit that is already pushed | `git revert <commit>` |

`reset` and `--amend` rewrite history: use them only on commits that have not been
pushed. `revert` adds a new commit that reverses an old one, so it is safe on shared branches.

## Stash

```bash
git stash                 # shelve uncommitted changes
git stash list
git stash pop             # bring the latest stash back and drop it
git stash apply stash@{1} # bring a specific stash back, keep it in the list
```

## Reflog: the safety net

```bash
git reflog                # every position HEAD has been at
git reset --hard HEAD@{2} # go back to one of them
```

Commits "lost" by a reset or a deleted branch can usually be recovered this way.

## Other useful tools

```bash
git cherry-pick <commit>  # copy one commit onto the current branch
git clean -n              # preview untracked files that would be removed
git clean -fd             # remove untracked files and folders
```
