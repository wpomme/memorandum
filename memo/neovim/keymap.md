## keymap

## noremap, silentの意味
- noremap
    - 他のショートカットキーの設定に連鎖させないようにする
- silent
    - キーの実行時に、画面下のコマンドラインに実行コマンドやメッセージを表示させない

# 例
```
-- 次のバッファへ移動 (Tab)
vim.api.nvim_set_keymap('n', '<Tab>', ':bnext<CR>', { noremap = true, silent = true })
-- 前のバッファへ移動 (Shift+Tab)
vim.api.nvim_set_keymap('n', '<S-Tab>', ':bprevious<CR>', { noremap = true, silent = true })
```

## keymapの重複を調査する
```
# checkhealthを実行すろと、which-keyプラグインの方でkeymapの重複を調べてくれる
:checkhealth

# コマンドラインモードでkeymapの詳細を調べる
:verbose map <your-keybinding>
# 例
:verbose map <C-b>
:verbose nmap <leader>f
```
