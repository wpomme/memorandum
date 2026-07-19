## bash - for 文

```bash
## パターン１
##
## man bashの中のSHELL GRAMMARという章のCompound Commandsという項に載っている
## 次で大体見つかるはず
man bash
/^SHELL GRAMMAR

## パターン１
## for name [ in word ] ; do list ; done
## nameがfor文の中で使える変数になる。[ in word ]は色々なパターンがあったと思うが、
## ここでは、コマンド置換としている。doの後のlistのところに処理を書いて、doneで終了
## 例:
for DIRS in `find "$HOME/repo/memorandum/memo" -type f`; do
  echo $DIRS
  # ls $DIRS > /dev/null 2>&1 || echo $DIRS
done
```
