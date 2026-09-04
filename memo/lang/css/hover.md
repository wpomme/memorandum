## hover: CSSの擬似クラス
- カーソルを要素の上にかざしたときに発動するスタイル

### 順番
- LVHA順で定義されるようにする
    - :link — :visited — :hover — :active

## 例
    - 擬似クラスを複数記載する場合はカンマで区切る
```css
.link-button:hover, :active {
    background-color: blue;
}
```
