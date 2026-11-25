---
tags: ["neovim", "register", "WIP"]
---
## Registers: Vimnのレジスタについて
### ドキュメント
    - `:h | registers`など

### レジスタの種類
- テキストやコマンドを保存する場所
- 10種類もある
1. 無名レジスタ(The unnamed register "")
    - 最後に使用されたレジスタ
    - "でアクセスできる

2. 番号付きレジスタ(10 numbered registers "0 to "9)
3. The small delete register "-
    - 一行以下の文字列が削除されたときにこのレジスタに文字列が入る
    - ただし、`x`で文字を消したときは使用されない

### WIP
```
4. 26 named registers "a to "z or "A to "Z
5. Three read-only registers ":, "., "%
6. Alternate buffer register "#
7. The expression register "=
8. The selection registers "* and "+
9. The black hole register "_
10. Last search pattern register "/
```
