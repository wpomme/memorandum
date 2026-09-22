## lsof: list open files - オープン中のファイルについて、その情報を得るためのコマンド

### 例: ポート8080によって開かれているファイルの情報を得るには
```bash
lsof -i:8080
# 次のような値が返ってくる
# COMMAND   PID USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
# node    25789   hy   32u  IPv6 0xc355a48837ad9ec6      0t0  TCP localhost:rwhois (LISTEN)
```

### 例: 特定のuserが開いているファイルの情報を得るには
```bash
lsof -u <USER>

## USERが開いているプロセス名の一覧を取得するには
lsof -u <USER> | cut -w -f1 | sort | uniq
```
