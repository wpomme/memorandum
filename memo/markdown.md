- markdown: markdownの記法に関するメモ
# 特殊文字(Special Characters)
## バックスラッシュ(\\)
<kbd>option</kbd> + <kbd>¥</kbd>

- Front Matter
    - Markdownファイルの先頭に記載されるメタデータのこと

- textlint
```bash
# textlintと日本語のスペース関連のプリセットをグローバルにインストール
pnpm add -g textlint textlint-rule-preset-ja-spacing

# ファイル名は必ず引用符で括る必要がある(自分の環境だけ？)
textlint --preset preset-ja-spacing "README.md"
```
