# Troubleshoot

## Breakpoints in IDE time out!
Hystrix commands by default run with a isolation strategy of THREAD.  This strategy by default has a timeout of 500 milliseconds.  There are two ways to work around this:
1. set default timeout to something huge
1. set isolation strategy to SEMAPHORE

It is recommended to set the isolation strategy to SEMAPHORE, but care must be taken if this is not test code that is timing out.  Don't leave the change to default in place unless it is intended!

To set the default isolation strategy make a file called `config.properties` available on the classpath with the following content:
```
hystrix.command.default.execution.isolation.strategy=SEMAPHORE
```

Examples of this can be found in unit tests where hystrix commands are used.  For full documentation refer to the [Hystrix Configuration](https://github.com/Netflix/Hystrix/wiki/Configuration) wiki.

## MongoDB is not up during the tests/debug
Check if there is another MongoDB running using the same IP and Port. You may use the command 'ps aux | fgrep mongodb' to get the PID of zombie process (this often occurs during the debug due the imediate shutdown or run two processs) and kill (using 'kill -9 PID') the process.
