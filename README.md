---
description: Mobingi Documentation
---

# Overview

{% hint style="warning" %}
**This product is already deprecated.**
{% endhint %}

## Overview

### Overview

[mobingi](https://github.com/mobingi/mobingi) is the official command line interface for [Mobingi](https://mobingi.com/) services.

To view a list of the available commands, just run mobingi without arguments:

```bash
$ mobingi
Command line interface for Mobingi API and services.

Usage:
  mobingi [command]

Available Commands:
  creds       manage your credentials
  help        help about any command
  login       login to Mobingi API
  rbac        manage role based access control features
  registry    manage your Mobingi docker registry
  reset       reset config to defaults
  stack       manage your stack
  svrconf     manage your server config file
  template    manage your ALM templates
  version     print the version

Flags:
      --token string    access token
      --url string      base url for API
      --rurl string     base url for Docker Registry
      --apiver string   API version (default "v3")
  -f, --fmt string      output format (values depends on command)
  -o, --out string      full file path to write the output
      --indent int      indent padding when fmt is 'json' (default 2)
      --timeout int     timeout in seconds (default 120)
      --verbose         verbose output
      --debug           debug mode when error occurs
  -h, --help            help for mobingi

Use "mobingi [command] --help" for more information about a command.
```

To get help for any command, pass the -h flag to the command. For example, to see help about the stack command:

```bash
$ mobingi stack -h
Manage your infrastructure/application stack.                    

Usage:                                                           
  mobingi stack [flags]                                      
  mobingi stack [command]                                    

Available Commands:                                              
  create      create a stack                                     
  delete      delete a stack                                     
  describe    display stack details                              
  list        list all stacks                                    
  pem         print stack pem file                               
  ssh         ssh to your instance                               
  update      update a stack                                     

Flags:                                                           
  -h, --help   help for stack                                    

Global Flags:                                                    
      --apiver string   API version (default "v3")
      --debug           debug mode when error occurs
  -f, --fmt string      output format (values depends on command)
      --indent int      indent padding when fmt is 'json' (default 2)
  -o, --out string      full file path to write the output
      --rurl string     base url for Docker Registry
      --timeout int     timeout in seconds (default 120)
      --token string    access token
      --url string      base url for API
      --verbose         verbose output

Use "mobingi stack [command] --help" for more information about a command.
```

