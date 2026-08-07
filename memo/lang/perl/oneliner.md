## Perl one-liners: Perlによるワンライナー
```bash
## ドキュメント: perlrunにperlコマンドのオプションの解説がある
man perlrun

## ドットファイルだけを取得
## -e: ワンライナーを実行するために使われてきたオプション。-eがあればファイル名を読み飛ばしてコマンドを実行する
ls -alGpF | perl -lane 'print if $F[-1] =~ /^\./'
```
