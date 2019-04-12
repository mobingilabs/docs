# Deployments

The following is the API reference for working with Ocean deployments. 

## Create a deployment

**Request**

```http
POST /v0/deployments HTTP1.1
Authorization: Bearer {token}

{template body}
```

**Response**

```http
HTTP 202
```

Check out [https://github.com/mobingi/ocean-template-examples](https://github.com/mobingi/ocean-template-examples) for examples about `{template body}`. For details on how to write Ocean templates, check out this [reference](https://docs.mobingi.com/v/ocean-en/template-2018-07-02).

## List deployments

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

```http
REQUEST
GET /v0/deployments HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 200
tbd
```

## Describe a deployment

**Request**

```http
GET /v0/deployments/{name} HTTP1.1
Authorization: Bearer {token}
```

`{name}` is the template (or deployment) name.

**Response**

```http
HTTP 200
```

Example response

```ruby
{
  "stacks":[
    {
      "name":"stack-name",
      "items":[
        {
          "name":"eksmaster",
          "resources":[
            {
              "key": "AWS::EC2::InternetGateway",
              "value": "igw-040e7443b67d8cda2"
            },
            {
              "key": "AWS::EC2::Route",
              "value": "aws-5-Route-1PR9K4JNZTQRY"
            }
          ],
          "status": "creating|updating|completed|failed"
        },
        {
          "name":"cfnextra",
          "resources":[
            {
              "key": "AWS::SNS::SNSTopic",
              "value": "arn:aws:sns:ap-northeast-1:...cfnextra-sample-snstopic"
            },
          ],
          "status": "creating|updating|completed|failed"
        }
      ]
    }     
  ]
}
```

## Delete a deployment

**Request**

```http
DELETE /v0/deployments/{templatename} HTTP1.1
Authorization: Bearer {token}
```
**Response**

```http
HTTP 202
```

