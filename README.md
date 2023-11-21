# Linux-commands

## process
To list any process listening to the port 8080:

``` lsof -i:8080 ```
To kill any process listen to port 8080:

``` kill $(lsof -t -i:8080) ```
or more violently:

``` kill -9 $(lsof -t -i:8080) ```
