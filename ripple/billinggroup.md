# BillingGroup

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

The following is the API reference for working with billing group.

## Create

create billing group information

**Role actions**

- `ModifyBillingGroup` 

**Request**

```http
POST /billinggroup HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

The following are some example request payloads for `{request body}`.

**{request body}**

```ruby
{
	"billinggroup_id":"Billing1",
	"billinggroup_name":"Billing1",
	"company_name":"Billing1 company",
	"phone":"03‐1234‐5678",
	"postal":"12345",
	"address":"123 street",
	"billing_title":"billing title",
	"personal":"personal name",
	"remarks":"test automation",
	"inv_aggregate":false,
	"invoices": {
		"aws": {
			"calc_type":"account",
		    "currency":"jpy",
		    "discount_calc_logic":"usageamount",
		    "discount_rate":0,
		    "discount_target_usage":"cloudpaywithfee",
		    "substitution_fee":"percent",
		    "substitution_fee_calc_target":"nondiscount",
		    "substitution_fee_calc_type":"allsum",
		    "substitution_fee_target_usage":"cloudpaywithfee",
		    "substitution_fix":0,
		    "substitution_rate":0,
		    "support_amount_target":"allusage",
		    "support_fee":"fix",
		    "support_fee_calc_target":"nondiscount",
		    "support_fix":0,
		    "support_rate":0,
		    "tax_rate":0
		}
  }
}
```

**{request body} description**


Field               | Type      | Required | Validation | Description
------------------  | --------- | -------- | ---------- | -----------
billinggroup_id     | *string*  | Yes      | -          | Billing group ID
billinggroup_name   | *string*  | Yes      | -          | Billimg group name
company_name        | *string*  | Yes      | -          | Company name
phone               | *string*  | No       | -          | Tel
postal              | *string*  | No       | -          | Postal
address             | *string*  | No       | -          | Address
billing_title       | *string*  | No       | -          | Invoice title
personal            | *string*  | No       | -          | Personal name
remarks             | *string*  | No       | -          | Memo
inv_aggregate       | *boolean* | Yes      | -          | Displaying invoice in bulk or by vendor
project_id          | *string*  | No       | -          | Project id
invoice_template_id | *string*  | No       | -          | Invoice template id
invoices            | [object]  | No       | -          | Invoice setting

**invoices object description**


Field               | Type      | Required | Validation | Description
------------------  | --------- | -------- | ---------- | -----------
calc_type           | *string*  | Yes      | - account <br> - tag                                        | Invoice calculation type
currency            | *string*  | Yes      | - jpy <br> - usd                                            | Currency
discount_calc_logic | *string*  | Yes      | - usageamount                                               | -
discount_rate       | *double*  | Yes      | 0.00 ~ 1.00                                                 | -
discount_target_usage         | *string* | Yes | - cloudpaywithfee <br> - cloudpayonly                   | -
substitution_fee              | *string* | Yes | - percent <br> - fix <br> - automatic <br> - usagetable | -
substitution_fee_calc_target  | *string* | Yes | - nondiscount <br> - discounted                         | -
substitution_fee_calc_type    | *string* | Yes | - allsum <br> - account                                 | -
substitution_fee_target_usage | *string* | Yes | - cloudpaywithfee <br> - cloudpayonly                   | -
substitution_fix              | *double* | Yes | 00 ~ 1000000                                            | -
substitution_rate             | *double* | Yes | 0.00 ~ 1.00                                             | -
support_amount_target         | *string* | Yes | - allusage                                              | -
support_fee                   | *string* | Yes | - fix <br> - percent <br> - aws_developer <br> - aws_business <br> - aws_enterprise | -
support_fee_calc_target       | *string* | Yes | - nondiscount <br> - discounted                         | -
support_fix                   | *double* | Yes | 0.00 ~ 1000000                                          | -
support_rate                  | *double* | Yes | 0.00 ~ 1.00                                             | -
tax_rate                      | *double* | Yes | 0.00 ~ 0.10                                             | Tax


**Response**

```ruby
HTTP 200

{
	"status":"success",
	"company_id":"RomwoEjdjhws",
	"billinggroup_id":"Billing1"
}
```

## List

get list of billing group informaiton

**Role actions**

- `ReadBillingGroup` 
- `ModifyBillingGroup` 

**Request**

```http
GET /billinggroup HTTP1.1
Authorization: Bearer {token}

```

**Response**

```ruby
HTTP 200

[
	{
	"company_id":"RomwoEjdjhws",
	"billinggroup_id":"Billing1",
	"billinggroup_name":"Billing1",
	"name":"Billing1 Company",
	"invoices":{
		"aws": {
			"calc_type":"account",
		    "currency":"jpy",
		    "discount_calc_logic":"usageamount",
		    "discount_rate":0,
		    "discount_target_usage":"cloudpaywithfee",
		    "substitution_fee":"percent",
		    "substitution_fee_calc_target":"nondiscount",
		    "substitution_fee_calc_type":"allsum",
		    "substitution_fee_target_usage":"cloudpaywithfee",
		    "substitution_fix":0,
		    "substitution_rate":0,
		    "support_amount_target":"allusage",
		    "support_fee":"fix",
		    "support_fee_calc_target":"nondiscount",
		    "support_fix":0,
		    "support_rate":0,
		    "tax_rate":0
		}
		"azure": {
			"calc_type":"account",
		    "currency":"jpy",
		    "discount_calc_logic":"usageamount",
		    "discount_rate":0,
		    "discount_target_usage":"cloudpaywithfee",
		    "substitution_fee":"percent",
		    "substitution_fee_calc_target":"nondiscount",
		    "substitution_fee_calc_type":"allsum",
		    "substitution_fee_target_usage":"cloudpaywithfee",
		    "substitution_fix":0,
		    "substitution_rate":0,
		    "support_amount_target":"allusage",
		    "support_fee":"fix",
		    "support_fee_calc_target":"nondiscount",
		    "support_fix":0,
		    "support_rate":0,
		    "tax_rate":0
		}
	},
	"contact":"personal name",
	"address":"123 street",
	"postal":"12345",
	"phone":"03‐1234‐5678",
	"title":null,
	"req_generate":null,
	"remarks":null,
	"inv_aggregate":null,
	"project_id":null,
	"project_code":null,
	"project_label":null,
	"project_currency":null,
	"language":"ja",
	"qrcode":false,
	"invoice_template_id":null,
	"custom_fields":null,
	"untagged_groups":null,
	"account":[],
	"tag":[]
	},
	...
]
```

## List details

**Role actions**

- `ReadBillingGroup` 
- `ModifyBillingGroup` 

**Request**

```http
GET /billinggroup/{id}/resource HTTP1.1
Authorization: Bearer {token}

```
request parameter for `{id}` is company_id.


**Response**

```ruby
HTTP 200

{
	"company_id":"RomwoEjdjhws",
	"billinggroup_id":"Billing1",
	"billinggroup_name":"Billing1",
	"name":"Billing1 Company",
	"invoices":{
		"aws": {
			"calc_type":"account",
		    "currency":"jpy",
		    "discount_calc_logic":"usageamount",
		    "discount_rate":0,
		    "discount_target_usage":"cloudpaywithfee",
		    "substitution_fee":"percent",
		    "substitution_fee_calc_target":"nondiscount",
		    "substitution_fee_calc_type":"allsum",
		    "substitution_fee_target_usage":"cloudpaywithfee",
		    "substitution_fix":0,
		    "substitution_rate":0,
		    "support_amount_target":"allusage",
		    "support_fee":"fix",
		    "support_fee_calc_target":"nondiscount",
		    "support_fix":0,
		    "support_rate":0,
		    "tax_rate":0
		}
		"azure": {
			"calc_type":"account",
		    "currency":"jpy",
		    "discount_calc_logic":"usageamount",
		    "discount_rate":0,
		    "discount_target_usage":"cloudpaywithfee",
		    "substitution_fee":"percent",
		    "substitution_fee_calc_target":"nondiscount",
		    "substitution_fee_calc_type":"allsum",
		    "substitution_fee_target_usage":"cloudpaywithfee",
		    "substitution_fix":0,
		    "substitution_rate":0,
		    "support_amount_target":"allusage",
		    "support_fee":"fix",
		    "support_fee_calc_target":"nondiscount",
		    "support_fix":0,
		    "support_rate":0,
		    "tax_rate":0
		}
	},
	"contact":"personal name",
	"address":"123 street",
	"postal":"12345",
	"phone":"03‐1234‐5678",
	"title":null,
	"req_generate":null,
	"remarks":null,
	"inv_aggregate":null,
	"project_id":null,
	"project_code":null,
	"project_label":null,
	"project_currency":null,
	"language":"ja",
	"qrcode":false,
	"invoice_template_id":null,
	"custom_fields":null,
	"untagged_groups":null,
	"account":[],
	"tag":[]
}
```


## Update

update billing group information.

**Role actions**

- `ModifyBillingGroup` 

**Request**

```http
PUT /billinggroup/{id} HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

The following are some example request payloads for `{request body}`.

**{request body}**

```ruby
{
	"billinggroup_id":"Billing1",
	"billinggroup_name":"Billing1",
	"company_name":"Billing1 Company",
	"phone":"03-123-4567",
	"postal":"1243",
	"address":"updateed address",
	"billing_title":null,
	"personal":"Personal name",
	"remarks":"Some remarks data",
	"inv_aggregate":false,
	"project_id":"{created_project_id}",
	"language": "ja"
}
```

Field                     | Type      | Required | Validation | Description
------------------------- | --------- | -------- | ---------- | -----------
`billinggroup_id`         | *string*  | Yes      | -                | Billing group ID
`billinggroup_name`       | *string*  | Yes      | length 1 ~ 100   | Billing group Name
`company_name`            | *string*  | Yes      | length 1 ~ 100   | Company name
`phone`                   | *string*  | No       | length 12 ~ 16   | Tel
`postal`                  | *string*  | No       | length 4 ~ 10    | Postal
`address`                 | *string*  | No       | length 1 ~ 100   | Address
`billing_title`           | *string*  | No       | length 1 ~ 100   | Invoice title
`personal`                | *string*  | No       | length 1 ~ 100   | Personal name
`remarks`                 | *string*  | No       | length 1 ~ 100   | Memo
`inv_aggregate`           | *boolean* | No       |                  | Displaying invoice in bulk or by vendor
`project_id`              | *string*  | No       |                  | Project id
`language`                | *string*  | No       | support: `ja`, `en` | Display invoice language setting


**Response**

```ruby
HTTP 200

{"status":"success"}
```


## Update invoice setting

**Role actions**

- `ModifyBillingGroup` 

**Request**

```http
PUT /billinggroup/{id}/invoices HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

The following are some example request payloads for `{request body}`.

**{request body}**

```ruby
{
  "invoices": {
    "calc_type":"account",
    "currency":"jpy",
    "discount_calc_logic":"usageamount",
    "discount_rate":0,
    "discount_target_usage":"cloudpaywithfee",
    "substitution_fee":"percent",
    "substitution_fee_calc_target":"nondiscount",
    "substitution_fee_calc_type":"allsum",
    "substitution_fee_target_usage":"cloudpaywithfee",
    "substitution_fix":0,
    "substitution_rate":0,
    "support_amount_target":"allusage",
    "support_fee":"fix",
    "support_fee_calc_target":"nondiscount",
    "support_fix":0,
    "support_rate":0,
    "tax_rate":0.10
  },
  "vendor":"{vendor}"
}
```

Field                           | Type      | Required | Validation | Description
------------------------------- | --------- | -------- | ---------- | -----------
`calc_type`                     | *string*  | Yes      | support: `account`,`tag`                        | 計算タイプ
`currency`                      | *string*  | Yes      | support: `jpy`,`usd`                            | 通貨
`discount_calc_logic`           | *string*  | Yes      | support: `usageamount`,`allamount`              | 値引き対象
`discount_rate`                 | *double*  | Yes      | support: 0 ~ 1                                  | 値引率
`discount_target_usage`         | *string*  | Yes      | support: `cloudpayonly` ,`cloudpaywithfee`      | 値引き計算方法
`substitution_fee`              | *string*  | Yes      | support: `percent`, `fix`, `automatic`, `table` | 代行手数料請求方法
`substitution_fee_calc_target`  | *string*  | Yes      | support: `cloudpayonly`, `cloudpaywithfee`      | 代行手数料計算対象
`substitution_fee_calc_type`    | *string*  | Yes      | support: `allsum`, `account`                    | 請求代行サービス計算方法
`substitution_fee_target_usage` | *string*  | Yes      | support: ['nondiscount', 'discounted']          | 請求代行手数料対象
`substitution_fix`              | *double*  | Yes      | support: 0 ~ 1,000,000                          | 代行手数料 固定
`substitution_rate`             | *double*  | Yes      | support: 0 ~ 1                                  | 代行手数料 (%)
`support_amount_target`         | *string*  | Yes      | support: `allusage`, `cloudpayonlywithfee`      | 表示なし
`support_fee`                   | *string*  | Yes      | support: - aws `percent`, `aws_developer`, `aws_business`, `aws_enterprise`, `fix` <br> - azure `percent`, `fix`  | サポート料請求方法
`support_fee_calc_target`       | *string*  | Yes      | support: `cloudpayonly`, `cloudpaywithfee`      | サポート料計算対象
`support_fix`                   | *double*  | Yes      | support: 0 ~ 1,000,000                          | サポート料 固定
`support_rate`                  | *double*  | Yes      | support: 0 ~ 1                                  | サポート料 %
`tax_rate`                      | *double*  | Yes      | support: 0 ~ 0.08                               | 消費税率 %

**Response**


```ruby
HTTP 200

{"status":"success"}
```

## Update free format

**Role actions**

- `ModifyBillingGroup` 

**Request**

```http
PUT /billinggroup/{id}/freeformat HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

The following are some example request payloads for `{request body}`.

**{request body}**

```ruby
{
	"additional_items":[
	{
		"enabled":true,
		"label":"testlabel",
		"unit_cost":1,
		"quantity":10000,
		"total":10000
	}
]
}
```


**Response**



```ruby
HTTP 200

{"status":"success"}
```

## Update Invoice Template

**Role actions**

- `ModifyBillingGroup` 

**Request**

```http
PUT /billinggroup HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

The following are some example request payloads for `{request body}`.

**{request body}**

```ruby
{
	"invoice_template_id": "abcdefg"
}
```


**Response**


```ruby
HTTP 200

{"status":"success"}
```

## Delete

**Role actions**

- `ModifyBillingGroup` 

**Request**

```http
DELETE /billinggroup/{id} HTTP1.1
Authorization: Bearer {token}

```


**Response**

```ruby
HTTP 200

{"status":"success"}
```