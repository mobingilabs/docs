# 概要

{% hint style="info" %}
Mobingi API はRESTの原則に則って構築されています。   
Mobingi API は予測しやすく、リソース志向のURLを持ちます。CORS \(Cross-Origin Resource Sharing\)もサポートしており、安全にAPIを利用できます。
{% endhint %}

## エンドポイント

[https://api.mobingi.com](https://api.mobingi.com) 

## バージョニング

現在有効なAPIバージョンは`v2`のみです。

## OAuth 認証

Mobingi APIは **OAuth** によるアプリケーションの認証が必要です。OAuth認証により取得したトークンはユーザー名・パスワードの代替となる働きをします。

OAuthトークンを取得するために下記のPOSTリクエストを実行してください。

```text
POST /v2/access_token
```

| **Parameters** | **Type** | **Required** | **Details** |
| --- | --- | --- | --- |
| client\_id | string | yes |  |
| client\_secret | string | yes |  |
| grant\_type | string | yes | この値は常に`client_credentials` |

Example Request:

```text
curl -X POST https://api.mobingi.com/v2/access_token \
-H "Content-Type: application/json" \
-d '{"grant_type":"client_credentials","client_id":"lg-5447826c870e7-xBV0OSJEN-tm","client_secret":"sFVYDoe08fxPjNgYvauYGOYCeXbOTE","grant_type":"client_credentials"}'
```

`access_token` 値を _Authorization_ のヘッダーに渡すことでAPIリクエストの作成が開始できます。

```text
Authorization: Bearer eyJ0eXAiOiJQiLCJhbGciOMeXzQfME...
```

