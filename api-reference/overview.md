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

