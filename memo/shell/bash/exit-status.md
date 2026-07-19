- EXIT STATUS
    - CLIコマンドの終了ステータス

man bash -> EXIT STATUS の章に載っている
0 - 正常終了
1 - 一般エラー
2 - 誤用法(引数や文法エラー)

厳密な規約はない

## 判定方法
- $?を使うこと(shell-variables.mdと同じ内容)
    - $?: 直前に実行したコマンドの実行ステータス
```bash
## これで確認できる
echo $?
```
