# Blue-green deployment

mobingi ALMは新しいコードをデプロイする際のダウンタイムを無くすため、Blue-Green Deploymentを使用しています。コードページのボタンをクリックするだけで簡単にコードのデプロイが可能です。

![](../../.gitbook/assets/code_1bgjp.png)

接続ボタンを押すとスタックの全サーバーに以下のワークフローが実行されます。

* コンテナイメージの更新
* リポジトリからコードのダウンロード
* 新しいコンテナの作成
* コンテナへのコードのインストール
* コンテナのテスト運用
* 成功した場合には全てのコネクションを新しいコンテナへと自動変更
* 10秒以内に古いコンテナを削除

## Blue-Green Deployment フロー

まず、全てのコンテナはBlue Containerとして知られるコンテナに送られます。

![](../../.gitbook/assets/bg-deploy2jp.png)

コードがデプロイされた際、新しいコードを持つ新しいGreen Containerが起動し内部でインストールを開始します。  


![](../../.gitbook/assets/bg-deploy3jp.png)

準備が完了した後、全てのトラフィックは新しいコンテナへと変更されます。しかしコネクションが存在する間は古いBlue Containerも稼働した状態を保ちます。

![](../../.gitbook/assets/bg-deploy4jp.png)

ほとんどのHTTPは10秒以内に完了しBlue Containerはシャットダウンされ、次のデプロイメントはBlue Containerに代わりGreen Containerにて行われます。

![](../../.gitbook/assets/bg-deploy5jp.png)

