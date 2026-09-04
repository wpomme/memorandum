## yard: ドキュメント生成のためのライブラリ

### 記法
- 次のドキュメントが参考になる
    - https://rubydoc.info/gems/yard/file/docs/GettingStarted.md#Declaring_Types
- YARD Type Parserというものもある
    https://yardoc.org/types.html

#### 例
- 戻り値がStringかnilの場合: `@return [String, nil]`
- キーが文字列で値がシンボルか数値の場合: `Hash{String => Symbol, Number}`
