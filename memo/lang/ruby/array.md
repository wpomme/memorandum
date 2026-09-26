---
tags: ["ruby", "array", "Creation", "Concatenation", "Data Structure"]
---
# Array: 配列について

## 配列の結合
- `<<, push, concat, +`について
    - <<: 配列の末尾に破壊的に要素を追加する
        ```ruby
        arr = [1,2,3]
        # => [1, 2, 3]
        arr << 4
        # => [1, 2, 3, 4]
        ```

    - push: 指定された要素を順番に配列の末尾に追加する
        - docs: https://docs.ruby-lang.org/ja/latest/method/Array/i/append.html
        ```ruby
        array = [1, 2, 3]
        array.push 4
        array.push [5, 6]
        array.push 7, 8
        # => [1, 2, 3, 4, [5, 6], 7, 8]
        ```

    - concat: 配列の末尾に破壊的に配列を追加する
        ```ruby
        arr = [1, 2, 3]
        # => [1, 2, 3]
        arr.concat([4, 5, 6])
        # => [1, 2, 3, 4, 5, 6]
        ```

    - +: 自分と他の配列同士を繋げた配列を生成して返す
