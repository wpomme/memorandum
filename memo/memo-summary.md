## summary: memorandumの集計情報
```bash
## 作成したファイルの数
## READMEなども含めた数
find memo -type f | wc -l
> 92

## 作成したファイルの総行数
## 最後のtotalに表示される
find memo -type f | xargs wc -l
> 1597 total

## lsやgrepでも集計情報が取得できそう
```

