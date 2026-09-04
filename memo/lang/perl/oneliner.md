## Perl one-liners: Perlによるワンライナー
```bash
## ドキュメント: perlrunにperlコマンドのオプションの解説がある
man perlrun

## ドットファイルだけを取得
ls -alGpF | perl -lane 'print if $F[-1] =~ /^\./'

## bashのマニュアルから章を抜き出すコマンド
man bash | perl -ne 'print if /^[A-Z]/'

## 対象ファイルについて、文字列の一括置換を行う場合(in-place編集)
git grep -l NOT_FOUND_MESSAGE | xargs -I@ perl -pi -e 's/NOT_FOUND_MESSAGE/READ_RESULT_IS_NOT_FOUND/g' @
```

## オプション
    - `man perlrun`にオプションのドキュメントがある。詳しくはそちらを参照すること。
- -e: perlのワンライナーを入力するために使用する。-eの後にワンライナーを入力すれば、perlはそのワンライナーを認識する
- -n: 一行ずつ処理する。ダイアモンド演算子と`while (<>) {...}`と同じ。`sed -n`や`awk`と似たような処理を実行する
- -p: -nと同じように一行ずつ処理するが、警告が-nより詳しい。perlにprintさせるだけなら、-nを使う。
- -i: in-placeで編集する。-iの後に何も指定しなければ、同じファイルを編集する。バックアップが不要なら`perl -i -e '...' <filename>`のようにして使う。
- -l: 行末処理の自動化を行う。入力時に改行を削除し、出力時に改行を追加する。
