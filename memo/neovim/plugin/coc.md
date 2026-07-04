## coc.nvim
    - 自動補完やリンターなど

## ドキュメント
:h coc-nvim | only

### 問題点
- `.vim/coc-settings.json`が勝手に生成されてしまう
-> neovim の起動時に設定ファイルが存在しない場合、`.vim/coc-settings.json`を自動で作成してしまう

## 使い方
- gd (coc-definition) で定義に移動した後に、元のページに戻るには
Ctrl + O
