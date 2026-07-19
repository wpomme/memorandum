## SHELL BUILTIN COMMANDS: 組み込みコマンド
- ドキュメント
    - 組み込みコマンドのドキュメントはman bash のSHELL BUILTIN COMMANDS に記載がある
    - 例えば、cd, command, 
```bash
man bash
## ^を付けないと結構いっぱい出てくる
/^SHELL BUILTIN COMMANDS
```

## builtinコマンドと外部コマンド
- bashには組み込みコマンドと外部コマンドがある
- `ls`などは外部コマンドである。
    - coreutils(GNU/Linux)かmacOSのシステムユーティリティとして提供されている外部コマンド
