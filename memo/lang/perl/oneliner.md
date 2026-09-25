---
tags: ["perl", "oneliner", "display", "edit", "substitute", "regex"]
---
## Perl one-liners: Perlによるワンライナー
```bash
## ドキュメント: perlrunにperlコマンドのオプションの解説がある
man perlrun

## grep系
### ドットファイルだけを取得
ls -alGpF | perl -lane 'print if $F[-1] =~ /^\./'

### bashのマニュアルから章を抜き出すコマンド
man bash | perl -ne 'print if /^[A-Z]/'

### 特定のフォルダから、"href="か"src="が含まれている行を抜き出すコマンド(正規表現の「選択」)
find packages/web/src | xargs -I@ perl -ne 'print if /href=|src=/' @

## sed系
### 対象ファイルについて、文字列の一括置換を行う場合(in-place編集)
git grep -l NOT_FOUND_MESSAGE | xargs -I@ perl -pi -e 's/NOT_FOUND_MESSAGE/READ_RESULT_IS_NOT_FOUND/g' @

### マッチする部分が正規表現ではなくて文字列である場合は、正規表現の最初に\Qを付ける
### 置換する文字列にも\Qを付けてしまうと、メタ文字も一緒に置換されてしまう
echo "_(expected).must_equal(actual)" | perl -p -e 's/\Q_(expected).must_equal(actual)/_(actual).must_equal(expected)/g'

### マッチングしたものを取り出す場合: https://perldoc.jp/docs/perl/5.22.1/perlretut.pod#Extracting32matches
### グループ化メタ文字()の中でマッチしたものは、$1, $2, ...などで取り出せる
### must_equalのカッコの中身にマッチさせて、その中身を_()の中に移動する
echo "_(expected).must_equal([:list, 'foo'])" | perl -p -e 's/\Q_(expected).must_equal(\E(.+)\)/_($1).must_equal(expected)/g'
# => _([:list, 'foo']).must_equal(expected)
```

## オプション
    - `man perlrun`にオプションのドキュメントがある。詳しくはそちらを参照すること。
- -e: perlのワンライナーを入力するために使用する。-eの後にワンライナーを入力すれば、perlはそのワンライナーを認識する
- -n: 一行ずつ処理する。ダイアモンド演算子と`while (<>) {...}`と同じ。`sed -n`や`awk`と似たような処理を実行する
- -p: -nと同じように一行ずつ処理するが、警告が-nより詳しい。perlにprintさせるだけなら、-nを使う。
- -i: in-placeで編集する。-iの後に何も指定しなければ、同じファイルを編集する。バックアップが不要なら`perl -i -e '...' <filename>`のようにして使う。
- -l: 行末処理の自動化を行う。入力時に改行を削除し、出力時に改行を追加する。

## 正規表現のオプション
- \Q: その正規表現のメタ文字をエスケープする
- \E: \Qなどのエスケープを\Eが追加された位置で終了させる
