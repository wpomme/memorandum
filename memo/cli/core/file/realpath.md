---
tags: ["bash", "CLI", "File and Directory", "display"]
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
