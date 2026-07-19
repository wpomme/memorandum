## zoxide: ナイスなcdコマンド
```bash
## ドキュメントやヘルプ
## z -hやman zだとドキュメントが参照できない
man zoxide
zoxide --help

## 記憶させたパスの消去
# zoxide editで記憶させたパスの一覧が表示される
zoxide edit

```
## 補足
- zoxide editで表示されるパス一覧とzoxide query -lで表示されるパスの一覧が一致しない
- たぶん、query -lの方は、存在しないパスは大体表示しないようにしてるっぽい
    - zoxide query -lから存在しないパスを抜き出そうとしたのだけど...


