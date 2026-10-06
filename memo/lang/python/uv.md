---
tags: ["CLI", "Python", "Package Manager", "Project Manager"]
---
## uv: Pythonのパッケージ＆プロジェクトマネージャー

### インストールなど
```bash
# homebrewでインストール可能
brew install uv
```

### プロジェクトの作成・実行
```bash
# helloフォルダが作成され、その中にプロジェクトの雛形が作成される
uv init hello

# プロジェクトの実行
cd hello/
uv run hello
```

### パッケージの追加・管理
```bash
# 対象のパッケージをrequestsとする
# シンプリに追加
uv add requests

# バージョン指定
uv add 'requests==2.31.0'

# requirements.txtから追加する場合は、-rオプションを指定する
uv add -r requirements.txt -c constraints.txt

# 削除
uv remove requests

# パッケージのアップデート
uv lock --upgrade-package requests
```
