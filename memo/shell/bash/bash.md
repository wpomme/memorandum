- bash
## TODO
man bashの章と項目をあらかじめ取得しておいて、memoに記載しておいてもいいかもしれない。
展開(EXPANSION) だけでいくつもの記事がある

##
### コマンド展開: Command Substitution
```
$(command)
# or
`command`
```

# 組み込みコマンド: SHELL BUILTIN COMMANDS 
    - 組み込みコマンドのドキュメントはman bash のSHELL BUILTIN COMMANDS に記載がある
    - 例えば、cd, command, 


## Tips
Control + l(C-l)で画面にある出力を消去できる  
詳しくはman bashのCommands for Movingを参照  
その他、(M-f)と(M-b)で単語単位で前後に移動できる、など  

### コマンドを例示するときのドル記号($)とハッシュ(#)の違い
- $ -> 一般ユーザー
- # -> rootユーザー

## コマンドの再実行
- 履歴展開 (History Expansion)
    - 直前のコマンドを実行する
```bash
$ !!
```

- インクリメンタルサーチ(Incremental search)
    - シェルプロンプトで`Ctrl - R`を押すと、コマンド履歴から逆順(Reverse)にインクリメンタル検索を実行できる

- 最近のstringで始まるコマンドを実行する
```bash
$ !string
```

## 条件付きリスト(conditional list)
### &&演算子
- cd dirが成功した場合にのみ、touch new.txtを実行
```bash
$ cd dir && touch new.txt
```

## ||演算子
- cd dirが失敗した場合、エラーコード1で終了する
```bash
$ cd dir || exit 1

# 例
## フォルダがなければ作成する
[ -d path/to/folder ] || mkdir -p path/to/folder
```



## 終了コード
- $? で確認できる。0なら成功、1なら失敗
```bash
$ echo $?
```

## プロセス置換 (Process Substitution)
- 構文
    - listの実行結果を、ファイルのように扱うことができる
```bash
<(list)
```
または、
```bash
>(list)
```

### 例
- diffなどの、引数としてファイルを要求するコマンドに使用する
```bash
diff <(list) <(list)
```

## 補足
プロセス置換は、実行されたコマンドの出力をファイル記述子と関連づける。echoを使うと関連づけられたファイル記述子の番号が確認できる。
```bash
$ echo <(ls)
```

## builtinコマンドと外部コマンド
- bashには組み込みコマンドと外部コマンドがある
- 組み込みコマンドは`man bash`でSHELL BUILTIN COMMANDSなどと検索すれば調べられる
- `ls`などは外部コマンドである。
    - coreutils(GNU/Linux)かmacOSのシステムユーティリティとして提供されている外部コマンド
    -> 組み込みでもcoreutils or macOSのシステムユーティリティでも、とりあえずbashに記事を書く
