## rebase: Reapply commits on top of another base tip

## 例
```bash
## 対話的にリベースする場合
### 例: 直前の二つのコミットをsquashしたい場合
### 直前の二つのコミットHEAD~2を指定して、リベース用のエディタを開く
git rebase -i HEAD~2
## -> 二番目のコミットのpickをs(squash)に変更して保存する。
```
