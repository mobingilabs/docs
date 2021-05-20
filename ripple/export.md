# Export

CSV出力に関するAPIリファレンスは以下の通りです。

## Get invoice csv\(account\)

請求書CSV\(account\)の出力

**Role actions**

* `ReadInvoice`
* `ModifyInvoice`

**Request**

```http
POST /export/csv/invoice_account/{month} HTTP1.1
Authorization: Bearer {token}
```

リクエストパラーメータの`{month}`のフォーマット: `yyyy-mm` 例: 2020-01

**Response**

```ruby
HTTP 200

{
  "status":"success",
  "url":"csv link"
}
```

CSVの内容

| Field | Description |
| :--- | :--- |
| BillingGroupID | 請求グループID |
| BillingGroupName | 請求グループ名 |
| CompanyName | 会社名 |
| Vendor | ベンダー |
| CustomerID | 顧客ID |
| CustomerName | 顧客名 |
| ServiceType | サービスタイプ |
| ServiceName | サービス名 |
| Charge | 金額 |
| DiscountCharge | 割引後額 |
| DiscountCharge - TaxFree | 割引後額 - 免税金額 |
| FreeFormat | フリーフォーマット金額 |
| CustomService | 請求サービス金額 |
| Tax | 消費税 |
| Total | 振込金額 |

## Get invoice csv\(tag\)

請求書CSV\(tag\)の出力

**Role actions**

* `ReadInvoice`
* `ModifyInvoice`

**Request**

```http
POST /export/csv/invoice_tag/{month} HTTP1.1
Authorization: Bearer {token}
```

リクエストパラーメータの`{month}`のフォーマット: `yyyy-mm` 例: 2020-01

**Response**

```ruby
HTTP 200

{
  "status":"success",
  "url":"csv link"
}
```

CSVの内容

| Field | Description |
| :--- | :--- |
| BillingGroupID | 請求グループID |
| BillingGroupName | 請求グループ名 |
| CompanyName | 会社名 |
| Vendor | ベンダー |
| Tag | タグ詳細 |
| ServiceType | サービスタイプ |
| ServiceName | サービス名 |
| Charge | 金額 |
| DiscountCharge | 割引後額 |
| DiscountCharge - TaxFree | 割引後額 - 免税金額 |
| FreeFormat | フリーフォーマット金額 |
| CustomService | 請求サービス金額 |
| Tax | 消費税 |
| Total | 振込金額 |

