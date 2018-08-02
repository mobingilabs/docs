# Create stack

```text
POST /v2/alm/stack
```

| **Parameters** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| vendor | string | no | Reserved namespace. Default value is always **aws**. Other supported values in Enterprise edition API are:  - _OpenStack_,  - _AliCloud_,  - _SBCloud_,  - _K5Cloud_. |
| cred | string | yes | The credential id to which Cloud vendor this stack should be deployed to. You need to set this value in [Save Credential](https://docs.mobingi.com/official/api/v2#save-credentials) API first. |
| region | string | yes | Eg. `ap-northeast-1` for AWS Tokyo region. |
| configurations | json | yes | \[see below\] |

| **Configuration** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| architecture | string | yes | Specify `art_single` for single stack or `art_elb` for load-balanced stack |
| type | string | yes | The server type, eg: `t2.small` |
| image | string | no | The docker registry path. You can either: - specify the full path, eg: `registry.mobingi.com/wayland/lamp`, or  - omit the domain part for pulling images from _hub.docker.com_directly, eg:`greyltc/lamp/` |
| dockerHubUsername | string | no | Specify your _username_ of the docker Hub if this is a private repository. |
| dockerHubPassword | string | no | Specify your _password_ of the docker Hub if this is a private repository. |
| min | int | no | The minimum instances in an autoscaling group if your `architecture` parameter is set to `art_elb`. Default value is 1. |
| max | int | no | The maximum instances in an autoscaling group if your `architecture` parameter is set to `art_elb`. Default value is 1. |
| spotRange | int | no | **AWS Only.** The percentage of which spot instances should be deployed within your autoscaling group range, set it between `0` to `100`.  For eg, if you have a total of 20 instances running in the autoscaling group, and `spotRange` is set to 50, then there will be a fleet of 10 spot instances and 10 on-demand instances. |
| nickname | string | no |  |
| code | string | no | A git repository URI, eg: `github.com/mobingilabs/default-site-php`  _Note_: you can always update the code repository after at any time after the stack creation is complete. |
| gitReference | string | no | A git repository branch tag, default value is `master` |
| gitPrivateKey | string | no | The private key for pulling your code if the repository is a private repo. |
| database | array | no | \[see below\] |
| elasticache | array | no | \[see below\] |

| **database** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| Engine | string | yes | Specify either `db_mysql` or `db_postgresql` |
| DBtype | string | yes | Eg. `db.m3.medium` |
| DBStorage | string | yes | Storage size in GB, between 5 to 6144 |
| ReadReplica1 | string | no | `true` or `false`, default is `false` |
| ReadReplica2 | string | no | \[same as above\] |
| ReadReplica3 | string | no | \[same as above\] |
| ReadReplica4 | string | no | \[same as above\] |
| ReadReplica5 | string | no | \[same as above\] |

| **elasticache** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| ElastiCacheEngine | string | yes | Specify either `Redis` or `Memcached` |
| ElastiCacheNodeType | string | yes | Eg. `cache.r3.large` |
| ElastiCacheNodes | string | yes | -Redis, Specify the number of Nodes between _1_ to _6_. One of them is the primary node, the others are the number of replicas.  -Memcached, Specify the number of Nodes between 1 to 20 |

Request Header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
    "region": "ap-northeast-1",
    "nickname": "sample stack",
    "vendor": "AWS",
    "cred": "AKIAJ2*********2DZLA",
    "configurations": {
        "spotRange":"50",
        "nickname":"sample stack",
        "min":"2",
        "max":"10",
        "type":"m3.medium",
        "architecture":"art_elb",
        "image":"mobingi/ubuntu-apache2-php7:7.1",
        "code":"github.com/mobingilabs/default-site-php",
        "region":"ap-northeast-1",
        "nodetype":"cache.r3.large",
        "database":
        [
            "DBStorage":"100",
            "Engine":"db_mysql",
            "DBtype":"db.t2.micro"
        ],
    }
}
```

Response Body:

```ruby
HTTP/1.1 200 OK
{
    "stack_id":"mo-5447826c880e8-v56QbKqA-tk",
    "status":"CREATE_IN_PROGRESS"
}
```

The stack creation usually takes 5 to 30 minutes to complete depends on your infrastructure's complexity. You can either log in to admin UI interface to see the stack creation progress, or make request to describe stack API.

In case if the response return a _CREATE-FAILED_ result, you may want to check your Cloud vendor's account to see if you've reached your account limit. Eg. there are a maxium of 20 VPCs per region per AWS account.

