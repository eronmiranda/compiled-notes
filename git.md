# One-liner Git Commands

## Force push current branch

```bash
git push --force origin $(git symbolic-ref --short HEAD)
```

## Upstream with main/master

```bash
git remote update --prune && git merge origin/master
```

## Get current Branch

```bash
git branch --show-current
```

## View commit history in oneline
```bash
git log --pretty=oneline
```
