# 環境構築

下記コマンドで新規作成
```bash
npm create electron-webpack
```

選択肢
- Select a framework: react
- Select a variant: TypeScript
- Select a package manager: npm

実行
```bash
npm run dev
```
ref.https://zenn.dev/sprout2000/articles/5d7b350c2e85bc  
  
## 注意事項

- 認証付プロキシ下では途中でフリーズするため、プロキシレス環境で実行する（npmやyarnのconfigでプロキシサーバを指定しても解決できず）
- プロキシレス環境でもnpmが勝手にプロキシ系の環境変数（http_proxy等）を見に行ってフリーズすることがあるので、設定している場合はexportで一時的に削除にしておく
- WSLの場合実行時に下記のようなエラーが出ることがある。

  > electron: error while loading shared libraries: libgbm.so.1: cannot open shared object file: no such file or directory
  
    下記コマンドで解決
    ```bash
    sudo apt-get update
    sudo apt-get install -y libgbm-dev
    ```