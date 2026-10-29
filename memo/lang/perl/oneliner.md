---
tags: ["perl", "oneliner", "表示", "edit", "substitute", "regex"]
---
## Perl one-liners: Perlによるワンライナー
### ドキュメント

            ## 総合的なドキュメント・目次
            man perl

            ## コマンドラインのオプションはperlrunに解説がある
            man perlrun

            ## 正規表現の場合は次の三つのうちのどれか
            man perlrequick
            man perlretut
            man perlre

### ファイルの編集と表示

            ## 1. 適当にファイルを作成する
            cat << EOF > foo.txt
            > aaa
            > bbb
            > ccc
            EOF

            ## 2. ファイルの置換は次のように指定する
            perl -i -pe 's/bbb/ddd/g' foo.txt

            ## 3. 確認してみる
            cat foo.txt
            # 次のように表示される
            # > aaa
            # > ddd
            # > ccc

            ## 2.1. 表示も行う
            ## perl -ne 'say if /ddd/' foo.txtだと表示できないみたいだ
            perl -ne 'print if /ddd/' foo.txt
            # 次のように表示される
            # > ddd


### 例
#### 正規表現の例
```perl
# 空行
/\A\s*\Z/
```

#### 検索・表示

            ### ドットファイルだけを取得
            ls -alGpF | perl -lane 'print if $F[-1] =~ /^\./'

            ### bashのマニュアルから章を抜き出すコマンド
            man bash | perl -ne 'print if /^[A-Z]/'

            ### 特定のフォルダから、"href="か"src="が含まれている行を抜き出すコマンド(正規表現の「選択」)
            find packages/web/src | xargs -I@ perl -ne 'print if /href=|src=/' @

#### 置換

            ### 対象ファイルについて、文字列の一括置換を行う場合
            git grep -l NOT_FOUND_MESSAGE | xargs -I@ perl -i -pe 's/NOT_FOUND_MESSAGE/READ_RESULT_IS_NOT_FOUND/g' @

            ### マッチする部分が正規表現ではなくて文字列である場合は、正規表現の最初に\Qを付ける
            ### 置換する文字列にも\Qを付けてしまうと、メタ文字も一緒に置換されてしまう
            echo "_(expected).must_equal(actual)" | perl -pe 's/\Q_(expected).must_equal(actual)/_(actual).must_equal(expected)/g'

            ### マッチングしたものを取り出す場合: https://perldoc.jp/docs/perl/5.22.1/perlretut.pod#Extracting32matches
            ### グループ化メタ文字()の中でマッチしたものは、$1, $2, ...などで取り出せる
            ### must_equalのカッコの中身にマッチさせて、その中身を_()の中に移動する
            echo "_(expected).must_equal([:list, 'foo'])" | perl -pe 's/\Q_(expected).must_equal(\E(.+)\)/_($1).must_equal(expected)/g'
            # => _([:list, 'foo']).must_equal(expected)


### コマンドラインのオプション
    - `man perlrun`にオプションのドキュメントがある。詳しくはそちらを参照すること。
- -e: perlのワンライナーを入力するために使用する。-eの後にワンライナーを入力すれば、perlはそのワンライナーを認識する
- -n: 一行ずつ処理する。ダイアモンド演算子と`while (<>) {...}`と同じ。`sed -n`や`awk`と似たような処理を実行する
- -p: -nと同じように一行ずつ処理するが、警告が-nより詳しい。perlにprintさせるだけなら、-nを使う。
- -i: in-placeで編集する。-iの後に何も指定しなければ、同じファイルを編集する。バックアップが不要なら`perl -i -e '...' <filename>`のようにして使う。
- -l: 行末処理の自動化を行う。入力時に改行を削除し、出力時に改行を追加する。

### 正規表現のオプション
- \Q: その正規表現のメタ文字をエスケープする
- \E: \Qなどのエスケープを\Eが追加された位置で終了させる
- \A: 文字列の先頭にマッチする
- \Z: 文字列の末尾にマッチする。ただし、後ろに改行文字があっても構わない。
- \z: 文字列の完全な末尾にマッチする
- \b: ワード境界アンカー。`/\bhunt/`とすると、shuntにはマッチしないが、huntingにはマッチする。
- \B: 非ワード境界アンカー。`/\bsearch\B/`とすると、searchesなどにはマッチするが、search, researchingにはマッチしない。
