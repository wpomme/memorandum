---
tags: ["Ruby", "Testing Framework"]
---
## minitest: 軽量なテスティングフレームワーク

- expectedとactualの位置
    - なぜか混同してしまうので
```rb
## spec形式
## この順番！
_(expected).must_equal(actual)

## assertion形式
assert_equal expected, actual
```

### teardownでそのテストケースの名前を出力するには
- teardown内でnameを呼び出せばいい
```ruby
def teardown
    puts "DB: #{name}" unless ~~~
end
```
