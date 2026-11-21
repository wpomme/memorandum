---
tags: ["bash", "CLI", "行数", "表示", "文字列処理", "how-to"]
---
## Line Number: 行数の表示を行うbashのCLI
1. 全行に番号を付ける場合`cat -n`
```bash
cat -n foo.txt
```

2. 空行を除いて表示`nl`
```bash
nl foo.txt
```

3. スクロースしながら表示`less -N`
```bash
less -N foo.txt
```
