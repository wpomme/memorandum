---
tags: ["Ruby", "Idiom"]
---
## Index in Ruby: Rubyでのインデックスの取り扱い
    - 取り扱いによく迷うので

### 方針
#### each_with_index => with_indexを使う
- rubocopで修正される
- with_indexは引数をとって、その引数から数え始めることができる(offset argument)

### 例
```ruby
str_arr = ['foo', 'bar', 'baz']

## インデックスの開始を１に定めた場合
str_arr.map.with_index(1) do |s, i|
  p s, i
end
# => "foo", 1, "bar", 2, ...
```

### injectと同時に使用する場合
- resultか真ん中のオブジェクトに割り当てられる値が何かバグったから違う方法で書いた方がいいかも
    - 書くとしたら`[1, 2, ...].map.with_index.inject(0) { |result, (item, index)| ... }`とする
