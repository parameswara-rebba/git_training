# Exercises

## 1. First repository
1. Create a folder, run `git init`, and add a `notes.txt` file.
2. Commit it. Change the file and commit again.
3. Use `git log --oneline` and `git diff HEAD~1` to see what changed.

## 2. Branch and merge
1. Create a branch `feature/a`, add a commit, and merge it into `main`. Was it a fast-forward?
2. Repeat, but add a commit on `main` before merging. What is different in `git log --graph`?

## 3. Cause and fix a conflict
1. Change the same line of `notes.txt` on `main` and on a new branch.
2. Merge, resolve the conflict, and complete the merge.

## 4. Undo things
1. Stage a file and unstage it again.
2. Make a commit, then undo it with `git reset --soft HEAD~1`.
3. Make a commit, then reverse it with `git revert`.
4. Run `git reset --hard HEAD~1`, then get the commit back using `git reflog`.

## 5. Remotes
1. Create an empty repository on GitHub and push your local one to it.
2. Push a feature branch, open a pull request, and merge it.
3. Pull the merged result back to your local `main`.
