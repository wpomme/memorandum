---
tags: ["bash", "CLI", "awk", "text", "edit"]
---
## awkの基本
パターンにマッチした行に対してアクションを実行する
```
pattern1 { action1 }
pattern2 { action2 }
```

## ビルトイン関数
- substr
strの一部を抽出する
```
substr(str, start[, length])
```

## オプション
- `-v`: awkから参照可能な変数を指定する

## セパレーター
- FS: 入力時のフィールドセパレーター
    - デフォルトは空白文字で、デフォルトだとタブや改行文字もセパレーターとして認識されるとのこと

- RS: 入力時のレコードセパレーター
    - デフォルトは改行文字


## 例
- 長い行を削除してファイルを表示する
```bash
cat error.log | awk 'length($0) <= 100 { print $0 }'
```

- フィールドセパレーターをタブ文字に指定する
-
```bash
memo tags -c | awk -v FS="\t" '$1 == 1 { print $2 }'
```
