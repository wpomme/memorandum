---
tags: ["bash", "CLI", "builtin", "Command inspection"]
---
## hash: bash builtinコマンド
- その環境で実行できるコマンドと、そのコマンドのパスの一覧が確認できる
```bash
hash | wc -l
# > 2692

hash | grep "^ls"
# > ls=/bin/ls
# > ...
# > ...
```
