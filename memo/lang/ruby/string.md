# String: 文字列クラスについて

## 文字列の結合
- `+, <<, concat`について、
    - <<, concatは破壊的変更である
        - サイズの大きいデータを生成するときなどに使う
        - `# frozen_string_literal: true`が指定されていると使えない

    1. <<: 文字列を破壊的に連結する
        ```ruby
        str = "foo"
        # => "foo"
        str << "bar"
        # => "foobar"
        ```

    2. concat: 複数の文字列を破壊的に連結する
        ```ruby
        str = "foo"
        # => "foo"
        str.concat "bar", "baz"
        # => "foobarbaz"
        str
        # => "foobarbaz"
        ```

    3. +: 元の文字列からその複製を返す
        - 文字列がfrozenされていても使える
        - パフォーマンスが悪くなるので、サイズの大きい文字列の生成をする際には注意すること

