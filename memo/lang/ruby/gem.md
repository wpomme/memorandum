- gem
    - Rubyのパッケージマネージャー
    - プロジェクトごとにパッケージを管理する場合はbundleを使う

- 例
```bash
# RubyGems のリポジトリを調べる
gem search -r <package>

## 例: pryに関係のあるパッケージを調べる
gem search -r pry

# gem のサブコマンド一覧を表示する
gem help commands

# gem list のhelp を確認する
gem help list
```

## Gemfileのバージョン指定
```ruby
## バージョンを固定する場合
gem "minitest", "6.0.6"

## 指定したバージョン以上を使う
gem "minitest", ">= 6.0.6"

## 6.0.6から6.1.0未満までを使う(悲観的なバージョン指定)
## バージョンの桁数によって指定する範囲が変わる
gem "minitest", "~> 6.0.6"

## これなら6.0以上7.0未満となる
gem "minitest", "~> 6.0"
```

- 自分でインストールしたgemの一覧
    - (1)インストール先を指定して確認するコマンドや、(2)インストール場所ごとに分けて確認するコマンドを組み合わせて確認する。
    1. `gem list -d`
    2. `gem environment`
