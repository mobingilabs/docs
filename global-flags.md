# Global flags

## Global flags

Global flags are all optional and can be applied to any subcommand. You can use '=' or whitespace when assigning a value to the flag. This applies to any command's local flags as well. For example, you can login using any of these commands:

```bash
# Using the '=' for assignment
$ mobingi login --client-id=foo --client-secret=bar
[mobingi]: info: Login successful.

# Using whitespace for assignment
$ mobingi login --client-id foo --client-secret bar
[mobingi]: info: Login successful.
```

`--token`

The access token to use in the command. By default, mobingi will save your access token to the config file after login \(see [login]() command\).

`--url`

The base API url to use in the command. By default, this is set to [https://api.mobingi.com](https://api.mobingi.com). You can use this flag if you are hosting your own backend. This is used by devs when testing the cli against the dev and test environments.

`--rurl`

The base registry url to use in the command. This is applicable to Mobingi Registry related commands. By default, this is set to [https://registry.mobingi.com](https://registry.mobingi.com). This is used by devs when testing the cli against the dev and test environments.

`--apiver`

Specify the API version used in the current command. The default version is v3. The only other supported version is v2.

`--fmt, -f`

Output format of the command. Valid values are: _raw_, _json_. Not all commands support this flag.

`--out, -o`

Full path of the file to write the command output. Not all commands support this flag.

`--indent`

Padding/indentation \(or the number of whitespaces to be added\) when the output format used is _json_. By default, this is set to 2.

`--timeout`

The timeout value \(in seconds\) for the command's http request \(if applicable\). By default, this is set to 120 seconds.

`--verbose`

When set to true, the command will print additional information during the command's execution.

`--debug`

When set to true, the command will print a stack trace when error occurs during the command's execution.

