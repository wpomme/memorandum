- tips
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
