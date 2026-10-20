---
tags: ["CLI", "tag"]
---
## git tag: コミットにタグ付けする

### 例: タグの履歴を追って、そのコミットに一時的に切り替える場合
```bash
# tagの一覧を表示する
git tag

# 特定のタグの詳細を確認する
git show <tag-name>

# そのタグのコミットを元に、そのコミットに一時的に切り替える
git switch --detach <commit-hash>

# 最後に、元のブランチに戻るには
git switch -
```
