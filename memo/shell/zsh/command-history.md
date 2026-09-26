---
tags: ["zsh", "documentation", "command history"]
---
## Zshのコマンド履歴について
    - fcコマンドを使う
    - コマンド履歴はtmuxだとウィンドウごとである

## ドキュメントの探し方
```zsh
man zshbuiltins
/fc
```

### Tips
- /historyで検索すると、"Same as fc -l" と記載がある
    - zshではhistoryコマンドの代わりにfc -lコマンドを使う

## fcコマンドの例
```zsh
# 直前のコマンド履歴を見る
# fc -l

# 数が指定できる
# fc -l 500

# 全ての履歴を番号なしで表示する
fc -ln 1

## コマンド履歴の集計
fc -ln 1 | sort | uniq -c | sort

## コマンドの文字列検索
fc -lm "git*"
```
