## EXPANSION: bashのコマンドや変数の展開
### ドキュメント
EXPANSIONという章がある。次のように検索すればその章に行ける
```
/^EXPANSION 
```

### 関係
- Command Substitution(コマンド展開)とも大きな関係がある

### コマンド展開: Command Substitution
- 次のようにしてコマンドを展開する
```
$(command)
# or
`command`
```

- *補足
man bashの中で、Substitutionを全部大文字にしてSUBSTITUTIONで検索しても見つからない。

### パラメーター展開: Parameter Expansion
- '$'がパラーメーター展開、コマンド展開、算術展開の橋渡しをする
- '{}'(ブレース)で囲まなくてもいいけど、他の文字列と混同することを防ぐ役割がある

```
## man bashの Parameter Expansionの冒頭からの引用
> The `$' character introduces parameter expansion, command substitution, or arithmetic expansion.
> The parameter name or symbol to be expanded may be enclosed in braces, which are optional but serve to protect
> the variable to be expanded from characters immediately following it which could be interpreted as part of the name.
```

### プロセス置換 (Process Substitution)
- 構文
    - listの実行結果を、ファイルのように扱うことができる
```bash
<(list)
```
または、
```bash
>(list)
```

### 例
- diffなどの、引数としてファイルを要求するコマンドに使用する
```bash
diff <(list) <(list)
```

## 補足
プロセス置換は、実行されたコマンドの出力をファイル記述子と関連づける。echoを使うと関連づけられたファイル記述子の番号が確認できる。
```bash
$ echo <(ls)
```
