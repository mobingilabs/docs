# Delete stack

```text
DELETE /v2/alm/stack/{stack_id}
```

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Response body:

```ruby
HTTP/1.1 200 OK
{   
    'status':'DELETE_IN_PROGRESS'
}
```

{% hint style="info" %}
It may take couple minutes to delete all related resources of your stack. Though the API will try to delete all resources \(such as ELB, security groups, subnets, keypairs, etc\) created by this stack, but in case some resource are linked/shared across other stacks, it may shown as a _DELETE-FAILED_ response, and you may need to manually resolve the conflict resources in your Cloud vendor account \(eg. AWS\) and call the API to delete the stack again.
{% endhint %}

