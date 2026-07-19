## bash: GNU Bourne-Again SHell

## Tips
Control + l(C-l)で画面にある出力を消去できる  
詳しくはman bashのCommands for Movingを参照  
その他、(M-f)と(M-b)で単語単位で前後に移動できる、など  

### コマンドを例示するときのドル記号($)とハッシュ(#)の違い
- $ -> 一般ユーザー
- # -> rootユーザー

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
