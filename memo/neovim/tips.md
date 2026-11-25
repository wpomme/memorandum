---
tags: ["neovim", "Tips", "Motion"]
---
## tips
`:messages`で過去のメッセージが見れる

- グローバル変数vimの中の変数の見方
:lua vim.print(vim.<variables>)
# 例: vim.pack のパッケージ一覧の見方(WIP)
:lua vim.print(vim.pack.get({}, {'name'}))

- 末尾の半角スペースを消去する
`%s/ $//g`

- undo, redo
    - undo: u
    - **redo: <C-R>**


- word-motion: 単語単位の移動
    - https://vim-jp.org/vimdoc-ja/motion.html#word-motions
    - `w`だけでなく、`W`や`e`でも移動できる

- object-motion: オブジェクト単位での移動
    - https://vim-jp.org/vimdoc-ja/motion.html#object-motions
    - `)`や`]]`で移動できる

- 連番の作成
    - ドキュメント: h | ^a
        - help | CTRL-A と同じ意味
1. 一行ごとに0を置く
2. 矩形ビジュアルモード(<C-v>)で、数字を選択する
3. g<C-a>で連番になる
    - 最初から連番だと、次は二の倍数の連番になる
