# Overview

{% hint style="info" %}
Mobingi API is organized around REST.   
Our API has predictable, resource-oriented URLs. We support CORS \(Cross-Origin Resource Sharing\), allowing you to interact securely with our API.
{% endhint %}

## Endpoint

[https://api.mobingi.com](https://api.mobingi.com) 

## Version

The current available API version is `v2` only.

## OAuth authentication

In order to interact with the API, your application must authenticate. Mobingi API handles this through **OAuth**. An OAuth token functions as a complete authentication request. In effect, it acts as a substitute for a username and password pair.

To get an OAuth token, make a POST request to:

```text
POST /v2/access_token
```

| **Parameters** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| client\_id | string | yes |  |
| client\_secret | string | yes |  |
| grant\_type | string | yes | This value is always `client_credentials` |

Example Request:

```text
curl -X POST https://api.mobingi.com/v2/access_token \
-H "Content-Type: application/json" \
-d '{"grant_type":"client_credentials","client_id":"lg-5447826c870e7-xBV0OSJEN-tm","client_secret":"sFVYDoe08fxPjNgYvauYGOYCeXbOTE","grant_type":"client_credentials"}'
```

You can then start making API requests by passing the `access_token` value to the **Authorization** header.

```text
Authorization: Bearer eyJ0eXAiOiJQiLCJhbGciOMeXzQfME...
```

