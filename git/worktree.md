# Work on two branches at once with `git worktree`

```sh
git worktree add ../app-hotfix hotfix/crash
git worktree list
git worktree remove ../app-hotfix
```

Each worktree is a separate checkout sharing the same `.git`, so there's no need
to stash to review a PR while a build is running.
