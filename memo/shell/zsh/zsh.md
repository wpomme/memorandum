---
tags: ["zsh", "documentation", "Tips", "completion"]
---
## zsh: Mac OSのデフォルトシェル
- コマンド履歴の検索、補完機能、zshzle(自作の関数とキーボードの操作をバインドすることができるみたい)が重要

## 履歴展開 (History Expansion)
- 最近のstringで始まるコマンドを履歴展開で補完して、実行したい場合
    - `!"string"`まで入力して、`Tab`キーを押すと、該当のコマンドが展開される。該当のコマンドが正しいことを確認して実行ができる。
```sh
$ !string
```

- zsh-completions
    - "zsh compinit: insecure directories"というwarningが出たら次を実行する
    1. `compaudit`を実行
    2. 信頼できないパスの一覧が出る。信頼できれば次を実行する
        - `chmod go-w '/path/to/file'`
        - `chmod -R go-w '/path/to/file'`

# ディレクトリ移動コマンドとzsh の設定
- 次の設定をdotfilesに記載してある
```zsh
# cd すると自動でpushd する
setopt autopushd

# pushd に同じディレクトリを重複させない
setopt pushdignoredups
```

- dirs, pushd, popdについて
```
# デフォルトだとディレクトリの遷移が見にくいので-v をalias に設定する
alias dirs="dirs -v"

## 数値の前に+ を付けなければいけないのが面倒...
# pushd +<number> でdirs -v で指定されたディレクトリに移動する
pushd +3

# popd +<number> でdir -v で指定されたディレクトリの履歴を消去する
popd +3
```
