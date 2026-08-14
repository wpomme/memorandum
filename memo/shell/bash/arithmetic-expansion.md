## bashの算術展開
### インクリメント
```bash
# letと++を使う方法
# commandとは別にインデックスが欲しい場合に使う
let ITER=0
for VAR in `command`; do
  echo $ITER
  let ITER++
done
```
