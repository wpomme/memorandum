---
tags: ["bash", "Notation", "Tips", "documentation"]
---
## Special Parameters: $?, $!など
### ドキュメントの探し方
    - ?, !など、それぞれの記号ごとに、$を付けて展開したときの説明が載っている
```bash
man bash
/Special Parameters
```

### 概要
- Special Parameterは$ を付けて展開する(Parameter Expansion)

#### 変数の一覧
- $#: スクリプトや関数に渡された引数の数
    - Ref: Expands to the number of positional parameters in decimal

- $?: 直前に実行したコマンドの実行結果。0ならTrueである。
    - Ref: Expands to the status of the most recently executed foreground pipeline.

- $!: 直前に実行したコマンドのプロセスID 
    - Ref: Expands to the process ID of the most recently executed background (asynchronous) command.
