---
tags: ["CLI", "Ruby", "Project Manager", "Dependency Management"]
---
## bundle: パッケージの依存関係を管理するためのCLIアプリ

### コマンドの一覧を見る方法(zsh)
```zsh
# gemと打った後、スペースを一つ入れてTabを押すと、サブコマンドの一覧が見れる
bundle <TAB>
```

### プロジェクトの作成
```bash
# Gemfileを作成する
bundle init

# 使いたいパッケージを追加する
bundle add minitest

# 作成されるGemfileに使いたいパッケージを記載してもいい
gem "rails", "~>8.1"

# パッケージをインストールする
bundle install
```

### プロジェクトごとに使用するコマンド
```bash
# そのプロジェクトの全てのgemを確認する
bundle show

# そのプロジェクトのパッケージを読み込んだ状態でirbにログインする
bundle exec irb
```

### rakeとbundle exec rakeの違い
- `rake` -> システムにインストールされた`rake`を使う
- `bundle exec rake` -> Gemfile.lockで固定されたバージョンの方の`rake`を使う

### bundle gem
```bash
# rubygem を作るための雛形を作成するコマンド
# <name> -> . とすればカレントディレクトリが指定される
# Gemfile や README が既にあると、上書きしていいかどうか聞かれる
bundle gem <name>
```

### bundler/gem_tasks
```ruby
# Rakefileでbundler/gem_tasksをインポートすると、build, release, installなどが行える
require "bundler/gem_tasks"
```
