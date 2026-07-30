## Ruby型検査
- テストコード
```ruby
## 配列の要素が全て同じなら真が戻り値になる
## Array#all?に検査したい型を入れる
require "minitest/expectations"

expected = seeds.all?(Memo::Model::Seed)

_(expected).must_equal(true)
# => true
```
