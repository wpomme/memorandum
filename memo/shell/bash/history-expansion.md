## HISTORY EXPANSION: コマンドの履歴を展開する
- ドキュメント: HISTORY EXPANSIONという章がある
```
man bash
/HISTORY EXPANSION
```

## コマンドの再実行
- 履歴展開 (History Expansion)
1. 直前のコマンドを実行する
```bash
$ !!
```

2. インクリメンタルサーチ(Incremental search)
- シェルプロンプトで`Ctrl - R`を押すと、コマンド履歴から逆順(Reverse)にインクリメンタル検索を実行できる

3. 最近のstringで始まるコマンドを実行する
```bash
$ !string
```

