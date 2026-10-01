---
tags: ["meta", "format"]
---
## format: メモフォルダをtextlintでフォーマットするための準備
```bash
# textlintと日本語のスペース関連のプリセットをグローバルにインストール
pnpm add -g textlint textlint-rule-preset-ja-spacing

# ファイル名は必ず引用符で括る必要がある(自分の環境だけ？)
textlint --preset preset-ja-spacing "README.md"
```
