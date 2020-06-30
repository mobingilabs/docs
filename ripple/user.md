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
  "exchange_rate": [
    {
      "month": "2020-04",
      "rate": 105.00
    }
  ],
  "pay_accounts": [],
  "service_fee": null,
  "company_name": "Company Name",
  "reseller_lng": null,
  "email": "info@alphaus.cloud"
}
```