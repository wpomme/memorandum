- React: フロントエンドライブラリ・UIフレームワーク

## Container / Presentational Component
- Container Component
    - データ取得・状態管理・ビジネスロジック
    - UIを持たず、Presenterにpropsを渡して描画を委譲する

- Presentational Component
    - UIを担当する
    - propsでデータとコールバックを受け取り、描画するだけ

- 組み合わせ方
```
# PresenterにContainer Componentを渡さないこと
Container
└─ Presenter
```
