## lua

### パッケージマネージャー
- `luarocks`を使う
    - homebrewからインストールする

### リンター
- `luacheck`を使う
    - luarocksからインストールする
        - ref: https://github.com/lunarmodules/luacheck#installation

- neovimの設定ファイルにLinterを実行
    - dotfiles/の下に`.luacheckrc`を作成する
        - globalsに`vim`を設定し、accessing undefined variable vimの警告をなくす

#### 実行
```bash
luacheck config/nvim/**/*.lua
```
