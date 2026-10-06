---
tags: ["Ruby", "print", "配列", "比較", "標準出力"]
---
## print: 標準出力への表示、puts, p, ppとの比較

### 配列とprint
```ruby
## 配列を定義する
arr1 = ["foo", "bar", "baz"]

## putsだと改行した文字列として表示される
puts arr1
foo
bar
baz

## printだと配列がそのまま標準出力に書き出される
## また、print自体は何も返さない
print arr1
["foo", "bar", "baz"] # => nil

## pだと配列をそのまま表示し、p自身も表示したものと同様のものを返す
p arr1
["foo", "bar", "baz"]
=> ["foo", "bar", "baz"]
```
