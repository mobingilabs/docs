# Dockerコンテナを介してカスタマイズ

mobingi ALMではお持ちのDockerイメージを利用しアプリケーションをデプロイすることが可能です。

{% hint style="info" %}
環境ファイルとcontainer\_statusファイルを持つように変更されていないDockerイメージは[Blue-Green Deployment](https://docs.mobingi.com/official/guide/jp/bg-deploy)が有効ではありません。コードのデプロイは`/var/www`フォルダに書き込まれます。
{% endhint %}

mobingi ALMはマシンのポート80と443に対して、コンテナのポート80と443をそれぞれ自動的にマッピングします。  
他のポートは無視されます。  


## 設定ファイル

もしカスタムDockerコンテナが設定ファイルを持っていない場合、起動時すぐに新しいコネクションを新しいコンテナに切り替えます。もしお客様のDockerコンテナが開始可能前にタスクを起動する必要がある場合、コネクションを受け入れる準備が整っているという信号が必要です。

また、設定ファイルがない場合でも、`/var/www`フォルダにのみコードをデプロイします。[Blue-Green Deployment](https://docs.mobingi.com/official/guide/jp/bg-deploy)を可能にし、コードデプロイのためのフォルダーのコードの配置を明確にするためにコンテナには以下が必要です。

* 1. ルートディレクトリ内の設定ファイル
* 2. コネクションを受け入れる準備ができた場合、スタートアップコマンドは`/var/log/container_status`ファイルに記述されている必要があります。

以下設定ファイルの例です:

```ruby
{
   "codeDirectory": "/srv/code"
}
```

