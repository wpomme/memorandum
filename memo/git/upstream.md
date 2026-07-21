## upstream: 追跡ブランチ

```bash
## git pushするときに-u(--set-upstream) originを付けると、そのブランチは追跡ブランチとなる
git push -u origin feature/foobar
# -> 次回以降はgit pushだけでpushできる

## 追跡ブランチが設定されているかどうかを確認するには
git branch -vv
# -> 三番目の項目に[origin/feature/foobar]などと表示されていれば、そのブランチは追跡ブランチ
## コマンドで抽出するなら:
git branch -vv | grep '\[origin/'

## 追跡ブランチを取り消すには
git branch --unset-upstream develop

## ただし、git pullするときにorigin developを追加する必要がある
git pull origin develop
```
