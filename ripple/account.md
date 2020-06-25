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

{}
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

```

**Response**

```ruby
HTTP 200

{}
```

## Delete

delete account information.

**Role actions**

- `ModifyAccount`

**Request**

```http
DELETE /accts/{customer_id} HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

```

**Response**

```ruby
HTTP 200

{}
```
