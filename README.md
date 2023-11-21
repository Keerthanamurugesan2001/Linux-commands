# Linux-commands

## Permission
``` sudo ```

To provide a temporary grant to users or user groups privileged access to system resources.
so that they can run commands that they cannot run under their regular accounts.

## process
To list any process listening to the port 8080:

``` lsof -i:8080 ```

To kill any process listen to port 8080:

``` kill $(lsof -t -i:8080) ```

or more violently:

``` kill -9 $(lsof -t -i:8080) ```

