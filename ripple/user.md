# User

{% hint style="warning" %}
This is still a draft version.
{% endhint %}

ユーザーのAPIリファレンスは以下の通りです。

## Get user

ユーザー情報の取得

**Role actions**

- `ModifySettings`

**Request**

```http
GET /user HTTP1.1
Authorization: Bearer {token}

```

**Response**

```ruby
HTTP 200

{
  "msp_start": "2020-01",
  "language": "ja",
  "invoices_info": {},
  "invoice_meta": {},
  "meta": {},
  "services": [],
  "username": null,
  "support_fee": [],
  "msp_id": "MSP-5aa311904d5d6",
  "invoice_layout": {},
  "service_discount": {},
  "months": [],
  "export_digit": "up",
  "exchange_rate": [],
  "pay_accounts": [],
  "service_fee": null,
  "company_name": "Company Name",
  "reseller_lng": null,
  "email": "info@alphaus.cloud"
}
```

**exchange_rate object例**

Field           | Type      | Description
--------------- | --------- | -------- 
 month         | *string*   | 月 format: `yyyy-mm`
 rate          | *double*   | 為替レート

```ruby
"exchange_rate": [
    {
      "month": "2020-04",
      "rate": 105.00
    }
]
```

**pay_accounts object例**

vendor : aws

Field             | Type      | Description
----------------- | --------- | -------- 
 vendor           | *string*  | ベンダー
 id               | *string*  | 支払いアカウント
 name             | *string*  | 支払いアカウント名
 bucket_name      | *string*  | aws s3 bucket名
 prefix           | *string*  | aws s3 bucket prefix
 report_name      | *string*  | aws s3 report名
 role_arn         | *string*  | aws iam role arn
 report_last_saved| *string*  | CUR更新日時

```ruby
"pay_accounts": [
    {
      "vendor": "aws",
      "id": "123456789109",
      "name": "Payer Account",
      "bucket_name": null,
      "prefix": null,
      "report_name": null,
      "role_arn": null,
      "report_last_saved": []
    }
]
```

vendor : azure

Field             | Type      | Description
----------------- | --------- | -------- 
 vendor           | *string*  | ベンダー
 id               | *string*  | 支払いアカウント
 name             | *string*  | 支払いアカウント名
 application_name | *string*  | azure application name
 application_id   | *string*  | azure application id
 commerce_id      | *string*  | azure commerce id

```ruby
"pay_accounts": [
    {
      "vendor": "azure",
      "id": "1234567",
      "name": "Payer Account",
      "application_name": null,
      "application_id": null,
      "commerce_id": null
    }
]
```