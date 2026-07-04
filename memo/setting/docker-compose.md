- docker-compose.yml
## 書式
```
## 左側がホスト側、右側がコンテナ側
## ホスト側のディレクトリ・ファイルをコンテナ側にマウントする
    volumes:
      - ./html:/usr/share/nginx/html
```
