## Virtual Text: 仮想のテキスト表示

### yankする方法
```
  方法1: :luaでdiagnosticメッセージを取得してレジスタに入れる
  :lua vim.fn.setreg('+', vim.diagnostic.get(0)[1].message)

  カーソル行のdiagnosticを取得する場合：
  :lua local d = vim.diagnostic.get(0, {lnum = vim.fn.line('.')-1}); vim.fn.setreg('+', d[1].message)

  方法2: Floating windowを開いてそこからyank
  :lua vim.diagnostic.open_float()

  方法3: :messages 経由（一時的に表示させる場合）
  1. :lua print(vim.diagnostic.get(0, {lnum = vim.fn.line('.')-1})[1].message)
  2. :messages で履歴を確認してコピー
```
