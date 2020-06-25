# Account

The following is the API reference for working with account.

## Create

create account information

**Role actions**

- `ReadAccount` 
- `ModifyAccount`

**Request**

```http
POST /accts HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

The following are some example parameter for `{vendor}`.

**{vendor}**

- aws
- azure

The following are some example request payloads for `{request body}`.

**{request body}**

```ruby
{
	"vendor":"aws",
    "customer_id":"012345678912",
    "account_id":"919999618919"
	"company_id":"AJfdivbDjhvbpE",
	"name":"ripple customer1",
	"note":null
}
```

**{request body} description**

Field         | Type      | Required | Validation | Description
------------- | --------- | -------- | ---------- | -----------
customer_id   | *string*  | Yes      | - AWS 12digits <br> - Azure 16~36digits | - AWS AccountID <br> - Azure SubscriptionID
account_id    | *string*  | Yes      | - AWS 12digits <br> - AZURE 7digits | - AWS PayerAccountID <br> - Azure BillingID
company_id    | *string*  | Yes      | -          | Billing group internal unique ID
vendor        | *string*  | Yes      | - supported: `aws`,`azure`  | 
name          | *string*  | Yes      | - length 3 ~ 100    | register customer name
note          | *string*  | No       | -          | note 

**Response**

```ruby
HTTP 200

{"status":"success"}

HTTP 400 customer id is already registered.

{
  "code":"5005",
  "message":"account function exception",
  "description":"Customer id already exists."
}
```

## List

get list of account information.

**Role actions**

- `ReadAccount` 
- `ModifyAccount`

**Request**

```http
GET /accts?vendor={vendor} HTTP1.1
Authorization: Bearer {token}

```

**Response**

```ruby
HTTP 200

[
  {
    "billinggroup_id":"Billing1",
    "billinggroup_name":"Billing1",
    "company_id":"AJfdivbDjhvbpE",
    "customer_id":"012345678912",
    "customer_name":"ripple customer1",
    "account_id":"919999618919",
    "vendor":"aws",
    "note":null,
    "payer":false,
    "service_discount":null,
    "project_id":null,
    "azure_customer_id":null
  },
  ...
]
```


## Update

update account information.

**Role actions**

- `ModifyAccount`

**Request**

```http
PUT /accts/{customer_id}/edit HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

**{request body}**
```

The following are some example parameter for `{customer_id}`.

**{customer_id}**

AWS AccountID or Azure SubscriptionID

The following are some example request payloads for `{request body}`.

**{request body}**

```ruby
{
	"vendor":"aws",
    "account_id":"919999618919"
	"company_id":"AJfdivbDjhvbpE",
	"name":"ripple customer1",
	"note":null
}
```

**{request body} description**

Field         | Type      | Required | Validation | Description
------------- | --------- | -------- | ---------- | -----------
account_id    | *string*  | Yes      | - AWS 12digits <br> - AZURE 7digits | - AWS PayerAccountID <br> - Azure BillingID
company_id    | *string*  | Yes      | -          | Billing group internal unique ID
vendor        | *string*  | Yes      | - supported: `aws`,`azure`  | 
name          | *string*  | Yes      | - length 3 ~ 100    | register customer name
note          | *string*  | No       | -          | note 

**Response**

```ruby
HTTP 200

{"status":"success"}

HTTP 400 customer id is not registered.

{
  "code":"5005",
  "message":"account function exception",
  "description":"Customer id is not exists."
}
```

## Delete

delete account information.

**Role actions**

- `ModifyAccount`

**Request**

```http
DELETE /accts/{vendor}/{id} HTTP1.1
Authorization: Bearer {token}

```

The following are some example parameter for `{vendor}`.

**{vendor}**

- aws
- azure

The following are some example parameter for `{id}`.

**{id}**

{id} format is `{customer_id}|{account_id}`. Request looks like `/accts/aws/012345678912|919999618919`

**Response**

```ruby
HTTP 200

{"status":"success"}
```
