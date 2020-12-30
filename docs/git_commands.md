# Git Commands

## Git Command list

For full documentation visit [git-scm.com](https://git-scm.com/docs/git).

### Take pull from a particular branch in remote

```sh
git pull origin <branch_name>
```

It is combination of git fetch + git merge
Note: Always prefer rebase over pull.

### Rebase your current local branch

```sh
git rebase <remote_base_branch> [<local_branch>]
```

Ex: git rebase origin/rel-2.0.12.001-sahil (If local branch is not given, it rebases it in current local branch)

### Add your changes in staging interactively

```sh
git add -p <files>
```

### Push changes to remote

```sh
git push <remote> <local branch>:<remote_branch>
```

Ex: git push origin rel-2.0.12.001-sahil:rel-2.0.12.001-sahil

### Push current branch changes to remote(also creates new remote branch if not present)

```sh
git push --set-upstream origin <remote_branch_name>
```

### Not track any file in git status

```sh
git update-index --assume-unchanged <file/folder/pattern>
```

### Get list of all remote branches

```sh
git ls-remote --heads
```

### Create a new branch and checkout it from a remote branch with tracking

```sh
git checkout -b <branch> --track <remote>/<branch>
```

### Create a new branch and checkout it from your current commit

```sh
git checkout <new_branch_name>
```

### Delete a local branch

```sh
git branch -d/D <branch_name> <multiple_branch_names>
```

D = delete even if not merged
d = delete only if merged

### Delete a remote branch

```sh
git push <remote> --delete <branch_name>
```

Ex: git push origin --delete rel-3.0

### Remove files from staging are

```sh
git reset HEAD file
```

### Remove unstaged changes

```sh
git checkout -- file
```

### Remove all staged and unstaged changes

```sh
git reset --hard
```

### Remove n last commits from local branch

```sh
git reset --hard HEAD~<n>
```

### Remove files from the tree

### Recover lost commit

Get the hash id of the commit you want to recover

```sh
git reflog
```

Reset the head to that commit

```sh
git reset --hard <hash>
```

### Cherry pick a commit

```sh
git cherry-pick <commit-hash>
```

### Logging with git

Logs in short:

```sh
git log --oneline
```

Full logs:

```sh
git log
```

Logs with graph:

```sh
git log --graph / git log --all --graph --decorate
```

### Open mergetool

```sh
git mergetool
```

Then, after solving the conflicts continue by:

```sh
git merge --continue
```

Or abort using

```sh
git merge --abort
```

### Check the code changes done in a file line by line

```sh
git blame <file_name>
```

Then using the sha1 id we can see the information for that commit using:

```sh
git show <sha1 id>
```
