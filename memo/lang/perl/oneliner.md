## Perl one-liners: Perlによるワンライナー
```bash
## ドキュメント: perlrunにperlコマンドのオプションの解説がある
man perlrun

## ドットファイルだけを取得
## -e: ワンライナーを実行するために使われてきたオプション。-eがあればファイル名を読み飛ばしてコマンドを実行する
ls -alGpF | perl -lane 'print if $F[-1] =~ /^\./'

## bashのマニュアルから章を抜き出すコマンド
## -n: 一行ずつ処理する。ダイアモンド演算子と`while (<>) {...}`と同じ。`sed -n`や`awk`と似たような処理を実行する
man bash | perl -ne 'print if /^[A-Z]/'
```
