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

```

**Response**

```ruby
HTTP 200

{}
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
