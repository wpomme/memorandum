## Start Project with Ruby: Rubyでプロジェクト・リポジトリを作成には

```bash
# 1. bundlerでGemfileを作成する
bundle init

# 2.1. 作成されるGemfileに使いたいパッケージを追加する
gem "rails", "~>8.1"

# 2.1.1. bundle installすればOK
bundle install

# 2.2. bundle addでも良さそう
bundle add minitest
```

- * なお、`bundle gem`コマンドでRubyGemを作成することができる
