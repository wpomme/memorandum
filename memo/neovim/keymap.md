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
