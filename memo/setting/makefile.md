- Makefile: クラシックなタスクランナーとファイル操作
- ドキュメント
    - gnuのドキュメントがWebにある
        - なんとなく記載が古いような...
    - man makeもある

## 文法

### ルールとターゲット、タスクランナーとして使用するには
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

# タスクランナーとして転用
# .PHONYに実行させたいタスクを入れて、そのタスクをtargetとして記載する
# -> ファイル作成のためのMakefileを.PHONYを使ってタスクランナーとして転用している

# 例
clean:
    rm *.o

.PHONY: clean
```
