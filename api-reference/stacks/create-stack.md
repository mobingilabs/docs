# Create stack

```text
POST /v2/alm/stack
```

| Parameters | Type | Required | Details |
| --- | --- | --- | --- | --- |
| vendor | string | no | Reserved namespace. Default value is always **aws**. Other supported values in Enterprise edition API are:  - _OpenStack_,  - _AliCloud_,  - _SBCloud_,  - _K5Cloud_. |
| cred | string | yes | The credential id to which Cloud vendor this stack should be deployed to. You need to set this value in [Save Credential](https://docs.mobingi.com/official/api/v2#save-credentials) API first. |
| region | string | yes | Eg. `ap-northeast-1` for AWS Tokyo region. |
| configurations | json | yes | \[see below\] |

