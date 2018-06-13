# Overview

Mobingi API is organized around REST. Our API has predictable, resource-oriented URLs. We support CORS \(Cross-Origin Resource Sharing\), allowing you to interact securely with our API.

## Endpoint

```text
https://api.mobingi.com
```

## Version

The current supported API version is `v3`.

## OAuth authentication

In order to interact with the API, your application must authenticate. Mobingi API handles this through **OAuth**. An OAuth token functions as a complete authentication request. In effect, it acts as a substitute for a username and password pair.

{% api-method method="post" host="endpoint" path="/v3/access\_token" %}
{% api-method-summary %}
OAuth authentication
{% endapi-method-summary %}

{% api-method-description %}
Get authentication token for subsequent API calls.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

