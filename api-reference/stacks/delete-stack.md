# スタックの削除

```text
DELETE /v2/alm/stack/{stack_id}
```

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Response body:

```ruby
HTTP/1.1 200 OK
{   
    'status':'DELETE_IN_PROGRESS'
}
```

{% hint style="info" %}
_注意_: スタックに付随する全てのリソースの削除には数分かかる場合があります。APIによりスタックの全てのリソース \(ELB, security groups, subnets, keypair など\) の削除が進行されますが、稀に一部のリソースを他のスタックと共有・連結している場合など、 _DELETE-FAILED_ と表示される場合があります。その場合、ご利用のクラウドベンダーのアカウント \(例: AWS\) から手動で競合箇所を解消し、再びスタック削除のAPIを叩く必要があります。
{% endhint %}

