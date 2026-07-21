## Suppress stdout and stderr: 標準出力と標準エラー出力の結果を表示しない場合
1. 標準出力だけ捨てる
```bash
ls ~/Downloads/ > /dev/null
```

2. 標準エラー出力だけ捨てる
```bash
ls ~/Downloads/do-not-exist-file.txt 2> /dev/null
echo $? # will return 1

## これは普通にlsの実行結果が表示される
ls ~/Downloads/ 2> /dev/null
```

3. 両方とも捨てる
```bash
## 従来の方法？
command -v ls 2>&1 > /dev/null

## Bash 4.0だと次の書き方でもOKらしい
command -v ls &> /dev/null
```
