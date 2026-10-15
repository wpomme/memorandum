## sqlite3: sqlite3 CLIの使い方など
### 使い方
```bash
## DBを読み込む
sqlite3 test.db
```

### 例
```
-- テーブルの一覧を表示する
.table

-- テーブルのスキーマを確認する
.schema <table_name>

-- 結果をHTMLにしてブラウザで表示する
    - .wwwの後にEnterを押して、その後にSQLを実行するとブラウザが起動して結果がテーブルで確認できる
.www
```
