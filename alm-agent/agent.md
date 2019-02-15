# Agent

## Usage  <a id="usage"></a>

ALM-agent is a very simple and easy-to-use tool. It can be used like a CLI \(not a Daemon\).

Executing ALM-agent will start the containers, the code will be deployed, and the command will be terminated.

To view a list of the available options and commands at any time, just run `alm-agent` with `--help, -h` arguments:

```bash
$ alm-agent --help
NAME:
   alm-agent

USAGE:
   alm-agent [global options] command [command options] [arguments...]

VERSION:
   v0.3.1504270893

COMMANDS:
     register  initialize alm-agent and start containers
     ensure    start or update containers
     stop      stop active container
     noop      run without container actions.
     help, h   Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --autoupdate, -U                  auto update before run
   --disablereport, -N               Do not send crash report to rollbar.
   --provider Provider, -P Provider  set Provider (default: "aws")
   --verbose, -V                     show debug logs
   --help, -h                        show help
   --version, -v                     print the version
```

## Global Options  <a id="global-options"></a>

* _--autoupdate,  -U_   Before running, ALM-agent checks the new version and updates the agent itself  if there is a new version. \(self-update\) 
* _--disablereport, -N_  We are using rollbar for error monitoring. If you do not want to send crash report to rollbar,   use this option. 
* _--provider Provider, -P Provider_  set Provider \(default: "aws", available providers: "aws", "alicloud", "k5", "localtest"\) 
* _--verbose, -V_  show debug logs 
* _--help, -h_  show help 
* _--version, -v_  print the version

