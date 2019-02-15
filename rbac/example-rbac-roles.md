# Example RBAC roles

## Allow all

```ruby
{
    "version": "2017-05-05",
    "statement": [
        {
            "effect": "allow",
            "action": "*",
            "resource": "*"
        }
    ]
}
```

## Allow UI login

```ruby
{
    "version": "2017-05-05",
    "statement": [
        {
            "effect": "allow",
            "action": "view:user.login",
            "resource": "*"
        }
    ]
}
```

## Deny credentials

```ruby
{
    "version": "2017-05-05",
    "statement": [
        {
            "effect": "allow",
            "action": "*",
            "resource": "*"
        },
        {
            "effect": "deny",
            "action": "*:credentials",
            "resource": ["AKIAJ7Z8PGXEZTIJOL6IQ"]
        }
    ]
}
```

## Deny list stacks

```ruby
{
    "version": "2017-05-05",
    "statement": [
        {
            "effect": "allow",
            "action": "*",
            "resource": "*"
        },
        {
            "effect": "deny",
            "action": "view:alm.stack",
            "resource": "*"
        }
    ]
}
```

## Deny list stacks by resource

```ruby
{
    "version": "2017-05-05",
    "statement": [
        {
            "effect": "allow",
            "action": "*",
            "resource": "*"
        },
        {
            "effect": "deny",
            "action": "view:alm.stack",
            "resource": ["mo-590fdb7bad55s-tJZpgRCBs-tk", "mo-590fdb7bad55s-ugMgQQ1TE-tk"]
        }
    ]
}
```

## Deny deleting stacks by resource

```ruby
{
    "version": "2017-05-05",
    "statement": [
        {
            "effect": "allow",
            "action": "*",
            "resource": "*"
        },
        {
            "effect": "deny",
            "action": "delete:alm.stack",
            "resource": ["mo-590fdb7bad55s-tJZpgRCBs-tk"]
        }
    ]
}
```

