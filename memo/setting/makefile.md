- Makefile: タスクランナーとファイル操作
- ドキュメント
    - Webにあるgnuのドキュメントを参照する
        - 誰かが個人的に翻訳して？アップロードしたもののようだ

## 文法
### 基本
```make
# 基本: ルールとターゲット
# 次のような定義が基本
<targets>: <prerequisites>
    <command>
# <prerequisites>に定められたファイルと最終更新日時を比較することにより、ターゲットの方が古ければコマンドを実行する
# また、ターゲットに定められたファイルが存在しない場合も、コマンドが実行される
```

### タスクランナーとして
```
# タスクランナーとして転用
# .PHONYに実行させたいタスクを入れて、そのタスクをtargetsとして記載する
# -> ファイル作成のためのMakefileを.PHONYを使ってタスクランナーとして転用している

# 例
clean:
    rm *.o

.PHONY: clean
```

## Makefileを指定して読み込むには
`make -f <Makefile>` ## `Makefile.wip`などを読み込みたい場合に使う

## Makefileの作り方
### デバッグ
1. `make -n`で実行されるコマンドを出力する
- 例
```make
make -n clean
```
2. 変数の値を表示するには`$(warning ...)`を使う
- 例
```make
## $(warning ...)を使う場合
$(warning objects: $(objects))

## 改行して見やすくするには標準出力にリダイレクトしてtrで整形する
make 2>&1 | tr " " "\n"

## このようにすると、ルール行やターゲット行をコメントアウトしたときに、`make`と打っただけでtestが実行されてしまう場合がある
## そのため、$(warning ...)を使うこと
test:;
    @echo $(objects)
```

## 命名規則
- ターゲットと変数は小文字にして、それぞれハイフン、アンダースコアで繋ぐべきとされる
    - Ref: https://www.gnu.org/software/make/manual/html_node/Standard-Targets.html#Standard-Targets
```make
test-files:
    @echo $(current_files)
```

## 変数を定義するには
- Makefileのユーティリティ関数を使うこと
```make
current_files = $(wildcard *)
exclude_files = Makefile
objects = $(filter-out $(exclude_files), $(current_files))
targets = $(patsubst %,$(HOME)/.%,$(objects))
```

## 自動変数
- 詳細はドキュメントを確認すること
    - https://ftp.gnu.org/old-gnu/Manuals/make-3.79.1/html_chapter/make_toc.html#TOC101
    - どの自動変数もそのディレクトリ名やファイル名だけを取得することが可能
- $@: ターゲット名を表す
- $<: 最初の依存するファイル名を表す(The name of the first prerequisite)
- $?: ターゲットより新しい全ての依存するファイル名を表す

## ターゲットごとに適用される依存ファイルを変えたい場合
```make
## パーセント(%)を使う
$(HOME)/.%: %
	cp $< $@
```

## サブディレクトリごとに存在するMakefileを利用するには
- Recursive Use of makeを参照すること
    - https://ftp.gnu.org/old-gnu/Manuals/make-3.79.1/html_chapter/make_5.html#SEC50

## その他: コマンドエコーを出力しないようにするには
- makeはコマンドの実行前にそのコマンドをターミナルに出力する
- その出力を抑えるには、コマンドの前に@をつける
```
$(HOME)/.%: %
	@echo $< $@
```
