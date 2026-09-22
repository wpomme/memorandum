## ls: list directory contents
```bash
## 再帰的にファイル名を表示する
ls -R memo/

## memo/フォルダの全てのファイルの詳細を表示する
## totalや空行は他のコマンドと組み合わせて消すのが一番良さそう
ls -Rl memo/

## -Tは-lと組み合わせると年数も表示できる
ls -RlT memo/

## さらに-tと組み合わせて、最終更新日時(mtime)が新しい順に表示することができる
ls -RTlt memo/

## なお、-uも付けると、最終アクセス日時(atime)が新しい順に表示することができる
### 最終更新時間 -> Last Modified Time, 最終アクセス時間 -> Last Access Time
ls -RTltu memo/

## aliasで定義されているlsの情報を確認
## -G: 色付け -F: ファイルの種別によって末尾に色々つける -p: ディレクトリの末尾にスラッシュを付ける
## * OSによってオプションの意味が結構変わるコマンドだったような...
command -v
> alias ls='ls -GpF'

## aliasで定義されているllの情報も確認
## -a: ドットファイルも表示する -l: 詳細表示（下記参照）
command -v ll
> alias ll='ls -alGpF'

## よく使うコマンド
### 更新順に表示するとき
ls -lt

### 容量順に表示するときは-Sオプションを使う
### さらに、-hで容量に単位がつく
### なお、-sオプションは、使用しているブロック数を表示する
ls -lS
```

## -lオプションについて

- `-l`: 詳細表示
   以下のデータを表示する
   file mode, number of links, owner name, group name,
   number of bytes in the file, abbreviated month, day-of-month file was last modified, hour file last modified, minute file last modified,
   and the pathname.
