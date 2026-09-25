---
tags: ["bash", "CLI", "text", "reverse"]
---
## rev: ファイルを連結させて最後の行から表示する

### 例
```bash
cat foo << EOF
abc
def
ghi
EOF

tac foo
# > ghi
# > def
# > abc
```

- revも参照すること
