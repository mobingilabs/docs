# スタックの作成

```text
POST /v2/alm/stack
```

| **Parameters** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| vendor | string | no | 予約済み名前空間。デフォルトの値は常に**aws**です。その他Enterprise edition APIでサポート済みの値は以下  - _OpenStack_  - _AliCloud_  - _SBCloud_  - _K5Cloud_ |
| cred | string | yes | 作成するスタックが実行されるクラウドベンダーの認証情報ID。最初にこの値を [認証情報の保存](https://docs.mobingi.com/official/api/v2/jp#save-credentials) APIに設定する必要があります。 |
| region | string | yes | 例: AWSの東京リージョンの場合 `ap-northeast-1` |
| configurations | json | yes | \[_下記参照_\] |

| **Configuration** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| architecture | string | yes | 単体スタックの場合は `art_single` 、ロードバランサ機能付きのスタックは `art_elb` |
| type | string | yes | サーバータイプ 例: `t2.small` |
| image | string | no | Dockerレジストリのパス。下記２通りの方法があります - 例: `registry.mobingi.com/wayland/lamp`のようにパス全体を指定 - _hub.docker.com_ から直接イメージを持ってくるためにドメイン部分を省き指定 例:`greyltc/lamp/` |
| dockerHubUsername | string | no | プライベートリポジトリを利用する場合のDocker Hubの _username_ の指定 |
| dockerHubPassword | string | no | プライベートリポジトリを利用する場合のDocker Hubの _password_ の指定 |
| min | int | no | `architecture` パラメーターを `art_elb` に設定した場合のAuto Scaling グループの最小インスタンス数。デフォルト値は 1 |
| max | int | no | `architecture` パラメーターを `art_elb` に設定した場合のAuto Scaling グループの最大インスタンス数。デフォルト値は 1 |
| spotRange | int | no | **AWSのみ有効** Auto Scaling グループ内に実行するスポットインスタンスの割合を `0` から `100` の間で指定。 例: 現在20台のインスタンスが実行しており、`spotRange`を50に設定した場合、10台のスポットインスタンスと10台のオンデマンドインスタンスが実行されます |
| nickname | string | no |  |
| code | string | no | GitリポジトリのURI 例: `github.com/mobingilabs/default-site-php`  _重要_: スタック作成が完了した後、いつでもコードの更新が可能です |
| gitReference | string | no | Gitリポジトリのブランチ。デフォルト値は `master` |
| gitPrivateKey | string | no | プライベートリポジトリを指定した場合のコードをpullするためのプライベートキー |
| database | array | no | \[_下記参照_\] |
| elasticache | array | no | \[_下記参照_\] |

| **database** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| Engine | string | yes | `db_mysql` もしくは `db_postgresql` を指定 |
| DBtype | string | yes | 例: `db.m3.medium` |
| DBStorage | string | yes | GB表記のストレージサイズ。 _5_ から _6144_ の間で指定。 |
| ReadReplica1 | string | no | `true` もしくは `false` デフォルトは `false` |
| ReadReplica2 | string | no | \[_同上_\] |
| ReadReplica3 | string | no | \[_同上_\] |
| ReadReplica4 | string | no | \[_同上_\] |
| ReadReplica5 | string | no | \[_同上_\] |

| **elasticache** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| ElastiCacheEngine | string | yes | `Redis` もしくは `Memcached` を指定 |
| ElastiCacheNodeType | string | yes | 例: `cache.r3.large` |
| ElastiCacheNodes | string | yes | -Redisの場合ノード数を _1_ から _6_ の間で指定。その内の _1_ つはプライマリノード、その他はレプリカの数となります。 -Memcachedの場合はノード数を _1_ から _20_ の間で指定。 |

Request Header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
    "region": "ap-northeast-1",
    "nickname": "sample stack",
    "vendor": "AWS",
    "cred": "AKIAJ2*********2DZLA",
    "configurations": {
        "spotRange":"50",
        "nickname":"sample stack",
        "min":"2",
        "max":"10",
        "type":"m3.medium",
        "architecture":"art_elb",
        "image":"mobingi/ubuntu-apache2-php7:7.1",
        "code":"github.com/mobingilabs/default-site-php",
        "region":"ap-northeast-1",
        "nodetype":"cache.r3.large",
        "database":
        [
            "DBStorage":"100",
            "Engine":"db_mysql",
            "DBtype":"db.t2.micro"
        ],
    }
}
```

Response Body:

```ruby
HTTP/1.1 200 OK
{
    "stack_id":"mo-5447826c880e8-v56QbKqA-tk",
    "status":"CREATE_IN_PROGRESS"
}
```

アプリケーションスタックの作成完了までにはインフラの構成により5分から30分かかります。ポータル画面にログイン、もしくは [スタック情報の取得](https://docs.mobingi.com/official/api/v2/jp#describe-stack) APIにリクエストを送ることでスタック作成の進捗が確認できます。

万が一 _CREATE-FAILED_ というレスポンスが返ってきた場合、登録されたクラウドベンダーのアカウントのリミットを確認してください。例: AWSの各アカウントのデフォルトでのVPC作成上限数は20

