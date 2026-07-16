## grep: 文字列検索

- 例
```bash
## -Rオブションを付ければfindからパイプで渡す必要もない
## -R: ディレクトリの中を再帰的に検索する
grep -R "ls" memo/

## memoフォルダの中にあるファイルを一括してgrepする
## xargsに渡すからかalias grep='grep --color=auto'が効かない
find memo -type f | xargs grep --color=auto "foo"

## --includeで特定のファイル名に該当するものだけを検索できる
grep -R "ls" --include="*.md" memo/

## -cオプションでそのファイルに何回その単語が現れたかを数えることができる
grep -Rc "ls" memo/

## -lオプションでその単語が現れたファイルだけを表示する
grep -Rl "ls" memo/
```
