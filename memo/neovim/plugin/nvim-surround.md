- nvim-surround
    - 文字列を記号で囲ってくれる
    - https://github.com/kylechui/nvim-surround

{example}
- ドキュメント
:h nvim-surround | only
    - ドキュメントに便利なエイリアス集などが載っている

## 使い方(ドキュメントから)

    Old text                    Command         New text
--------------------------------------------------------------------------------
    # 単語単位でスペースを入れずにシンボルでくくる -> ysiw
    surr*ound_words             ysiw)           (surround_words)
    surr*ound_words             ysiw(           ( surround_words )
    # 現在のカーソルから文末までシンボルでくくる
    *make strings               ys$"            "make strings"
    # くくってあるシンボルを消す -> ds
    [delete ar*ound me!]        ds]             delete around me!
    remove <b>HTML t*ags</b>    dst             remove HTML tags
    # くくってあるシンボルを変更する -> cs<old-symbol><new-symbol>
    'change quot*es'            cs'"            "change quotes"
    <b>or tag* types</b>        csth1<CR>       <h1>or tag types</h1>
    delete(functi*on calls)     dsf             function callsv
