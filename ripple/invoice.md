# Invoice

請求関連のAPIリファレンスは以下の通りです。


## Get Account total cost list

アカウント合計一覧の取得

**Role actions**

- `ReadInvoice`
- `ModifyInvoice`

**Request**

```http
GET /invoice/{month}/details HTTP1.1
Authorization: Bearer {token}

```
リクエストパラーメータの`{month}`のフォーマット: `yyyy-mm` 例: 2020-01

**Response**

```ruby
HTTP 200

{
  "accounts": [
    {
      "customer_id": "012345678987",
      "customer_name": "customer 1",
      "total": 431,
      "total_exchanged": 43100,
      "adjustment_entries": [
        {
          "name": "upfront - Sign up charge for subscription: 000000000, planId: 000000000",
          "amount": 2,
          "amount_exchanged": 200
        }
      ]
    },
    {
      "customer_id": "123456789875",
      "customer_name": "customer 2",
      "total": 6,
      "total_exchanged": 600,
      "adjustment_entries": [
        {
          "name": "upfront - one-time fee for 1 year All Upfront ap-southeast-1 EC2 Savings Plan ID:0000000000 ",
          "amount": 1,
          "amount_exchanged": 100
        }
      ]
    }
  ],
  "billing_groups": [
    {
      "billing_group_id": "bgid1",
      "billing_group_name": "bg1",
      "vendor": "aws",
      "tax_excluded_amount": 0,
      "tax_excluded_amount_exchanged": 0,
      "tax": 0,
      "total_amount_exchanged": 0
    },
    {
      "billing_group_id": "bgid2",
      "billing_group_name": "bg2",
      "vendor": "aws",
      "tax_excluded_amount": 437,
      "tax_excluded_amount_exchanged": 43700,
      "tax": 4370,
      "total_amount_exchanged": 48070
    }
  ]
}
```

accountsの詳細

Field              | Type      | Description
------------------ | --------- | -----------
customer_id        | *string*  | 顧客ID
customer_name      | *string*  | 顧客名
total              | *double*  | $金額(税抜)
total_exchanged    | *double*  | 換算後金額(税抜)
adjustment_entries | *list*    | 請求書に含んだ再計算請求データの一覧


billing_groupsの詳細

Field                  | Type      | Description
---------------------  | --------- | -----------
billing_group_id       | *string*  | 請求グループID
billing_group_name     | *string*  | 請求グループ名
vendor                 | *string*  | ベンダー
tax_excluded_amount    | *double*  | $合計金額(税抜)
tax_excluded_amount_exchanged    | *double*  | $換算後合計金額(税抜)
tax                    | *double*    | 消費税金額
total_amount_exchanged | *double*    | 合計請求金額

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