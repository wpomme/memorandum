## gitlab: コード管理プラットフォーム

### SSHキー問題
- SSHキーを手順通りに設定してもすぐdeniedとなってしまっていた
    - SSHキーが複数あると~/.ssh/id_rsaかid_ed25519を読み取ってしまう
    - そのため、次のドキュメントに従って適切なキーを設定すること
        - https://docs.gitlab.com/user/ssh_troubleshooting/#error-permission-denied-publickey
