- pnpm: パッケージマネージャー
```bash
## exec: プロジェクトのスコープでコマンドを実行
pnpm exec textlint

## 他のコマンドと被らなければexecは省略可能
pnpm textlint

## pnpm dlx (alias pnpx): レジストリから直接取得し、コマンドを実行
pnpx create-vue my-app
pnpm dlx create-vue my-app
# ドキュメントにはpnxのaliasesがpnpm dlx, pnpxとあるが、pnxだけが今の環境だと動かない
# ref: https://pnpm.io/ja/cli/pnx

# コマンドのグローバルインストールも可能
pnpm add -g textlint

# グローバルコマンドのリストを確認
pnpm list -g

# そしてアンインストールする場合
pnpm uninstall -g textlint
```
