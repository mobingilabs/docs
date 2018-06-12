# 環境変数

mobingi ALMでは、作られたスタックに合わせて、各リソースの情報が自動で環境変数へセットされます。 このことにより、RDS や ElastiCache などの個々の設定を確認する必要がなく、コードに環境変数さえセットしておけば、すぐにアプリケーションから利用できるようになります。

また、独自の環境変数をセットすることも可能です。

## デフォルト環境変数

スタック作成状況に合わせて、以下の環境変数が自動で設定されます。

**RDS \(MySQL, PostgreSQL\) の場合**

* `MO_DATABASE_NAME`: データベース名。
* `MO_DATABASE_USERNAME`: データベースユーザ名。
* `MO_DATABASE_PASSWORD`: データベースパスワード。
* `MO_DATABASE_PORT`: ポート番号。
* `MO_DATABASE_HOST`: マスターアドレス。
* `MO_DATABASE_SLAVE1_HOST`, `MO_DATABASE_SLAVE2_HOST`... : スレーブアドレス（スレーブの個数分）。
* `MO_DATABASE_SLAVE_HOSTGROUP`: スレーブアドレスグループ（スレーブアドレスのカンマ区切りフォーマット）。

**Redis の場合**

* `MO_REDIS_ENDPOINT`: プライマリーエンドポイント。
* `MO_REDIS_NODE1_ENDPOINT`, `MO_REDIS_NODE2_ENDPOINT`... : ノードエンドポイント（ノードの個数分）。
* `MO_REDIS_NODE_ENDPOINTGROUP`: ノードエンドポイントグループ（ノードアドレスのカンマ区切りフォーマット）。
* `MO_REDIS_PORT`: ポート番号。

**Memcached の場合**

* `MO_MEMCACHED_ENDPOINT`: コンフィグレーションエンドポイント。
* `MO_MEMCACHED_PORT`: ポート番号。

## 環境変数を設定する

スタック作成後、スタックの設定画面より環境変数を設定できます。

変更ボタンをクリックすると、新しいコンテナが起動します。古いコンテナから新しいコンテナへの切替が完了すると、入力した環境変数が使用できるようになっています。

![](../../.gitbook/assets/environment-variablesjp.png)

