# Invoice

請求関連のAPIリファレンスは以下の通りです。

## Get Invoice list

請求書一覧の取得


**Role actions**

- `ReadInvoice`
- `ModifyInvoice`

**Request**

```http
GET /invoices/{month} HTTP1.1
Authorization: Bearer {token}

```
リクエストパラーメータの`{month}`のフォーマット: `yyyy-mm` 例: 2020-01

**Response**

```ruby
HTTP 200

{
  "total": {
    "stock":108850,
    "sales":108850,
    "azure_stock":0,
    "azure_sales":0
  },
  "billinggroup": [
    {
      "company_id":"company1",
      "name":"company1",
      "billinggroup_id":"billinggroup1",
      "billinggroup_name":"billinggroup1",
      "project_id":null,
      "project_code":null,
      "project_label":null,
      "project_currency":null,
      "month":"2020-12",
      "invoice_no":"2020-12billing1",
      "created_data": {
        "aws": {
          "invoice_no":"2020-12billing1",
          "calc_type":"account",
          "currency":"jpy",
          "discount_rate":0.02,
          "discount_target_usage":"cloudpaywithfee",
          "discount_calc_logic":"usageamount",
          "tax_rate":0.10,
          "support_fee":"fix",
          "support_rate":0,
          "support_fee_calc_target":"nondiscount",
          "support_fix": 0,
          "substitution_fee":"percent",
          "substitution_rate":0,
          "substitution_fix":0,
          "substitution_fee_calc_target":"nondiscount",
          "substitution_fee_target_usage":"cloudpaywithfee",
          "substitution_fee_calc_type":"allsum",
          "exchange_rate":102.45,
          "memo":null,
          "additional_items": []
        },
        "azure":null
      },
      "saved_data": {
        "aws": {
          "invoice_no":null,
          "calc_type":"account",
          "currency":"jpy",
          "discount_rate":0.02,
          "discount_target_usage":"cloudpaywithfee",
          "discount_calc_logic":"usageamount",
          "tax_rate":0.10,
          "support_fee":"fix",
          "support_rate":0,
          "support_fee_calc_target":"nondiscount",
          "support_fix":0,
          "substitution_fee":"percent",
          "substitution_rate":0,
          "substitution_fix":0,
          "substitution_fee_calc_target":"nondiscount",
          "substitution_fee_target_usage":"cloudpaywithfee",
          "substitution_fee_calc_type":"allsum",
          "exchange_rate":102.45,
          "memo":null,
          "additional_items": []
        },
        "azure":null
      },
      "default_data": {
        "aws": {
          "invoice_no":null,
          "calc_type":"account",
          "currency":"jpy",
          "discount_rate":0.02,
          "discount_target_usage":"cloudpaywithfee",
          "discount_calc_logic":"usageamount",
          "tax_rate":0.10,
          "support_fee":"fix",
          "support_rate":0,
          "support_fee_calc_target":"nondiscount",
          "support_fix":0,
          "substitution_fee":"percent",
          "substitution_rate":0,
          "substitution_fix":0,
          "substitution_fee_calc_target":"nondiscount",
          "substitution_fee_target_usage":"cloudpaywithfee",
          "substitution_fee_calc_type":"allsum",
          "exchange_rate":null,
          "memo":null,
          "additional_items": []
        },
        "azure": {
          "invoice_no":null,
          "calc_type":"account",
          "currency":"jpy",
          "discount_rate":0,
          "discount_target_usage":"cloudpaywithfee",
          "discount_calc_logic":"usageamount",
          "tax_rate":0.10,
          "support_fee":"fix",
          "support_rate":0,
          "support_fee_calc_target":"nondiscount",
          "support_fix":0,
          "substitution_fee":"percent",
          "substitution_rate":0,
          "substitution_fix":0,
          "substitution_fee_calc_target":"nondiscount",
          "substitution_fee_target_usage":"cloudpaywithfee",
          "substitution_fee_calc_type":"allsum",
          "exchange_rate":null,
          "memo":null,
          "additional_items": []
        }
      },
      "accounts": [
        {
          "account_id":"012345678912",
          "customer_id":"012345678912",
          "customer_name":"customer1",
          "vendor":"aws",
          "service_discount":null
        },
        ...
      ],
      "create_time":"2020-12-21T11:26:55+09:00",
      "update_time":null,
      "total": {
        "aws":108850,
        "azure":0
      },
      "language":"ja"
    },
    ...
  ]
}
```