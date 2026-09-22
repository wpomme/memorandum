## sed: stream editor

## 例
```bash
# 1.1. gitリポジトリで対象のファイルの中の命名を置換したい場合
## 置換コマンドのところの-eを省略するとエラーが出る
## たぶんBSD版のsedを使っているMac限定のコマンド
git grep -l 'foo' | xargs sed -i '' -e 's/foo/bar/g'

# 1.2. ls を使ったファイルの中身の置換
ls | xargs sed -i '' s/foo/bar/g

# 2. ファイル名の一括リネーム
# 2.1. lsと組み合わせる
ls | sed "p;s/test/foo-test/" | xargs -n 2 mv


## その他、オプションの使い方など
### lsでフォルダを除外して、ファイル名だけを表示するには
```bash
$ ls -p | grep -v /
```

## オプションの詳細
- p: sedで変換される前の文字列も表示する
- i: 拡張子を指定して上書き(BSD version) -> macのsedはBSD  
    -> 空の文字列を指定すればバックアップなしの上書きになる  
    上書き(GNU version)  

