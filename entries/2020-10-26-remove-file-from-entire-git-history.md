---
title: Remove file from entire Git history
date: 2020-10-26
tags: git
---

Use `git filter-branch` command with `git rm` as a filter.

eg. I want to remove all `package-lock.json` since commit `xxxxx`

```shell
git filter-branch -f --index-filter "git rm -rf --cached --ignore-unmatch package-lock.json" xxxxx..HEAD
```

Next, verify if the diff includes only the contents of the file to be deleted.

```shell
git diff origin/main # or other branch on origin remote
```

Lastly, force push the commit.

```shell
git push -f
```
