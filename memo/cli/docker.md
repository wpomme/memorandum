# docker CLI: dockerを操作するためのCLI
## 起動しているdocker containerにログイン
```
docker exec -it <NAMES or CONTAINER ID> <Shell to login>
```
# 使用したことのあるコマンド
## cp
```
# ホストからコンテナへファイルをコピー
# 例: ホストのデータをdevコンテナの/homeへコピー
docker cp ./share_data/world-db dev:/home
```

## dockerコンテナの整理
```bash
#! /bin/sh
CONTAINER_ID=$(docker ps -aq)

for ID in $CONTAINER_ID
do
    docker stop $ID
    docker rm $ID
done
```
