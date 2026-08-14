## Arguments: Rubyの引数の取り扱いについて
- キーワード引数
```ruby
### 出典: https://www.ruby-lang.org/ja/news/2019/12/12/separation-of-positional-and-keyword-arguments-in-ruby-3-0/#what-is-deprecated
## キーワード引数を渡したい場合は次の形式にすべき
foo(k: expr)
foo(**expr)

## キーワード引数を受け取りたい場合は次の形式にすべき
def foo(k: default)
def foo(k:)
def foo(**kwargs)
```
