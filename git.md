# One-liner Git Commands

Below are useful Git one-liner commands for common tasks

## Force Push Current Branch

Forcibly push your current branch to the remote repository:

```bash
git push --force origin $(git symbolic-ref --short HEAD)
```

**Explanation:**

- `git symbolic-ref --short HEAD` - gets the name of the current branch.
- `git push --force origin <branch>` - forcefully pushes changes, rewriting history if necessary.

## Upstream with main/master

Fetch and merge the latest changes from the `main`/`master` branch:

```bash
git remote update --prune && git merge origin/master
```

**Explanation:**

- `git remote update --prune` - updates all remote tracking branches and removes deleted ones.
- `git merge origin/master` - merges the latest changes from `origin/master`.

## Get current Branch

Display the name of the current branch:

```bash
git branch --show-current
```

## View commit history in one-line

Show a formatted commit history into a single-line compact entries: 

```bash
git log --pretty=oneline
```
