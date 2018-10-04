# git rebase

## What is `git rebase`
Take commits from a branch and replay them at the end of another branch

## Why is `git rebase`
* Useful to integrate recent commits without unnecessary merging or merge conflicts that have to be resolved
* Maintain a cleaner, more linear and readable project history that makes easier for developers to track down bugs
* Ensure topic(feature) branch commits of each developer apply cleanly back to the `master` branch

## How is `git rebase`
* `git rebase master` - Rebase the current branch to the tip(end) of the `master` branch
* `git rebase master new-feature` - Rebase the `new-feature` branch to the tip of the `master` branch
* `git rebase --onto newbase upstream branch` - Rebase the `upstream` branch to the tip of the `newbase` branch
* `git rebase --onto 9291f0c88 master new-branch` - Undo a rebase by rebasing to a former `merge-base` SHA
* `git rebase --interactive master new-feature` - Modify commits as they are being replayed
* `git rebase --interactive HEAD~3` - Rebase last 3 commits onto the same branch but with the opportunity to modify them
* `git rebase --continue` - Record changes after resolving rebase conflicts and keep going down the chain of commits that are waiting to be rebased
* `git rebase --skip` - Bypass this current commit and keep going with the rest of the commits in the chain that are waiting to be rebased
* `git rebase --abort` - Cancel rebasing the current branch

### Useful commands for `git rebase`
* `git log --graph --all --decorate --oneline` - Visualize branch commits
* `git merge-base master new-feature` - Return the commit where the topic branch diverges
* `git reset --hard ORIG_HEAD` - Undo a rebase unless `ORIG_HEAD` has changed again that is a temporary variable used by Git to keep track of where things were when it's doing a rebase, a reset or a merge
* `git pull --rebase` - Fetch from remote then rebase instead of merging
* `git pull --rebase=preserve` - Preserve locally created merge commits and not flatten them
* `git pull --rebase=interactive` - Modify commits
