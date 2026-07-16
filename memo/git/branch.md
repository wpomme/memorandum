- branch: ブランチの作成など
```bash
# 基本: ブランチの作成
git branch <branch>

# 特定のコミット・ブランチから新しいブランチを作成するが、そのブランチには切り替えない場合
git branch <branch> <commit>

# ブランチを新規作成して、そのブランチに切り替えるならgit switchが使える
git switch -c <branch>
```
