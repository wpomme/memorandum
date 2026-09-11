## テストアサーションについて
- いつもexpectedとactualを逆に書いている気がする......。
- 文献がいつもexpectedとactualが逆なような......

### 期待値と実際の値
- expected(期待値): テストを実行する側が、こうあるべきとして定義する値
- actual(実際の値): テストを実際に実行して得られる値

### Ruby
minitestのassert, specは次の順番でactual, expectedを書く
```ruby
### assert
assert_equal expected, actual

### expectation
_(actual).must_equal(expected)
```
