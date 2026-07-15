- git squash
```bash
# git squashしてマージ
git merge --squash origin/feature/foo

# コンフリクトの事前確認
git merge --no-commit --no-ff feature/foo
```
