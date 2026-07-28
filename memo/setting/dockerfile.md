## Dockerfile: Dockerイメージをビルドするための設定ファイル

### 例
```
## 例: 簡単なlinux環境を作成して、ホームディレクトリと一般ユーザーを設定する
## busyboxはUNIXのCLIが一通り揃っているdockerイメージ
FROM busybox:latest

## j
RUN adduser -h /home/hy -u 1000 /bin/sh hy

WORKDIR /home/hy

USER hy
```
