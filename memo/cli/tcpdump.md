---
tags: ["CLI", "Network"]
---
## tcpdump: ネットワークの交信ログを取得
- 使い方
```bash
## 対象のインターファイスを指定すること
tcpdump -i en0

## パケット回数を10回に制限して、その内容をASCII文字で出力する
tcpdump -i en0 -c 10 -A

## 使用できるインターフェイスの一覧
tcpdump -D

## アプリケーションのサービス名で絞り込む
tcpdump -i en0 port https
### dnsは"domain"と指定する
tcpdump -i en0 port domain
## ホスト名でなくポート番号で指定するな-nnを指定する
tcpdump -i en0 port -nn 443
```

## ポート番号とサービス名の定義ファイル
- `/etc/services`を確認すること
