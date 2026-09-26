---
tags: ["bash", "documentation", "operator", "syntax"]
---
## 演算子

## ドキュメントの探し方
```bash
# SHELL GRAMMAR
# => Lists
# の節にドキュメントがある
man bash
/SHELL GRAMMAR
/  Lists
```

## 条件付きリスト(conditional list)
### &&演算子
- cd dirが成功した場合にのみ、touch new.txtを実行
```bash
$ cd dir && touch new.txt
```

## ||演算子
- cd dirが失敗した場合、エラーコード1で終了する
```bash
$ cd dir || exit 1

# 例
## フォルダがなければ作成する
[ -d path/to/folder ] || mkdir -p path/to/folder
```

