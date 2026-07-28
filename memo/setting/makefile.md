- Makefile: クラシックなタスクランナーとファイル操作
- ドキュメント
    - gnuのドキュメントがWebにある
        - なんとなく記載が古いような...
    - man makeもある

## 文法
### 基本
```Makefile
# 基本: ルールとターゲット
# 次のような定義が基本
<target>: <依存するファイル>
    <command>
# -> Make <target> でcommandが実行される
#    ただし、<target>が存在しない場合と、<target>よりも新しい依存するファイルが存在する場合にコマンドが実行される

# 例
hello: hello.c 
	gcc -o hello hello.c

# make helloを実行すればgcc -o hello hello.cが実行され、hello.cがコンパイルされる
```

### 、タスクランナーとして
```
# タスクランナーとして転用
# .PHONYに実行させたいタスクを入れて、そのタスクをtargetとして記載する
# -> ファイル作成のためのMakefileを.PHONYを使ってタスクランナーとして転用している

# 例
clean:
    rm *.o

.PHONY: clean
```

## Makefileを指定して読み込むには
`make -f <Makefile>` ## `Makefile.wip`などを読み込みたい場合に使う

## デバッグ
`make -n`で実行されるコマンドを出力する


## その他: 記号の意味など
- @echoとすると、echoコマンドが標準出力に表示されなくなる
