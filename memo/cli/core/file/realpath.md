---
tags: ["bash", "CLI", "File and Directory", "表示"]
---
## realpath: 実体の方のパスを返す
- How to
```bash
realpath <filename>
```

- ユースケース
```bash
# フルパスを取得してpbcopyに渡す
realpath <filename> | pbcopy
```
