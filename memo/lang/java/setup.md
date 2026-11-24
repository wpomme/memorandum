---
tags: ["Java", "Setup"]
---
## Java setup: Javaプロジェクトのセットアップ
### インストール・パス
- インストール
    - homebrewを使った

- パス
    - `brew info java`で分かる

### gradleによるプロジェクトのセッツアップ(WIP)
- gradleのインストール
    - homebrewを使った

- パスなどのセットアップ
    - gradleのドキュメントを確認すること
        - https://docs.gradle.org/current/userguide/installation.html
        - #JAVA_HOMEが必要

- プロジェクトのセットアップ
    - `gradle init`を実行する
        - javaのバージョンは`java -version`で確認すること
    - * Application => Java => Single application projectを選択する
        - まだLibraryを使うような場面がない
        - Basicは空のテンプレートが出来るだけ

- 実行
    - 補足: `java path/to/App.java`でもファイルの実行は可能
```bash
./gradlew run

## なお、./gradlewのタスク一覧は次のコマンドで確認可能
./gradlew tasks

## その他、runコマンドのヘルプは次の通り
./gradlew help --task run

## テストの実行
./gradlew test
```
