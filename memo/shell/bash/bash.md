---
tags: ["bash", "documentation", "Tips"]
---
## bash: GNU Bourne-Again SHell

## ドキュメントの探し方
- manページを確認することが基本: `man bash`
- 特に重要な章を次にリストアップしておく
```plain
# bashの組み込みコマンドに関する説明が載っている
# echo, cd, alias, type, command, etc...
SHELL BUILTIN COMMANDS

# コマンドや変数の展開について
EXPANSION
```

## bashの章を抜き出すコマンド
```bash
## 章だけを抜き出す
man bash | perl -ne 'print if /^[A-Z]/'

## 章と節を抜き出す
man bash | perl -ne 'print if /^[A-Z]|^\s{3}[A-Z]/'
```

## Tips
Control + l(C-l)で画面にある出力を消去できる  
詳しくはman bashのCommands for Movingを参照  
その他、(M-f)と(M-b)で単語単位で前後に移動できる、など  

### コマンドを例示するときのドル記号($)とハッシュ(#)の違い
- $ -> 一般ユーザー
- # -> rootユーザー

## 複数の文字列を変数に入れるとき
- `read`を使う。`while`やパイプと組み合わせる。
```bash
echo 'aaa bbb ccc' | while read A B C
do
  echo $A, $B, $C
done
# > aaa, bbb, ccc
```
