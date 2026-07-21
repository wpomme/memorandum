## pull: リモートからブランチを取得し、ローカルのブランチとマージする

### ローカルとリモートの履歴が分岐していた場合のwaringについて
1. pull.ff only: fast-forwardできる場合だけpull。分岐していたらエラー
2. pull.rebase true: ローカルのコミットをリモートブランチの先頭に載せる
3. pull.rebase false: マージコミットを作成して統合する

#### 設定方法
```bash
# 1.の場合
git config --global pull.ff only

# 2.の場合
git config --global pull.rebase true
```
