---
tags: ["CLI", "git", "Branching and Merging"]
---
## git merge
```bash
# git squashしてマージ
git merge --squash origin/feature/foo

# コンフリクトの事前確認
git merge --no-commit --no-ff feature/foo
```
