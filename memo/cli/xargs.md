## 例
- -Iコマンド
### コマンドに渡す引数の場所を指定する
```bash
echo 01\ Black\ Rain.aiff | tr " " - | xargs -I{} mv 01\ Black\ Rain.aiff {}
```

- -nコマンド
### コマンドに渡す引数の数を制御する
- できるだけ多くの入力文字列を受け入れる
```bash
ls | xargs echo
```

- 一つのechoコマンドにつき一つの引数を渡す
```bash
ls | xargs -n1 echo
```

- findとの組み合わせ
拡張子のあるファイルパスを取得して、行数を数える  
findに-print0を指定して、改行の代わりにヌル文字でファイルパスのリストを区切る  
また、xargsに-0を指定して、空白の代わりにヌル文字を入力セパレーターとして認識する  
```bash
$ find . -type f -name "*.*" -print0 | xargs -0 wc -l
```
