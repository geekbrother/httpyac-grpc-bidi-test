# gRPC bidirectional stream testing using httpyac tool

## What the purpose of this

The examples above demonstrate how the [httpyac](https://httpyac.github.io/) can be used in the automated CI testing
using the httpyac CLI and exit codes check.

## Test examples

This is an example of how to use [httpyac](https://httpyac.github.io/) for the gRPC bidirectional stream testing.

To run the tests you need to clone the repository, [install httpyac](https://httpyac.github.io/guide/installation_cli.html), and execute the following command:

```
httpyac *.grpc --all
```

This will run `testbidiFail.grpc` and `testbidiSuccess.grpc` test files.

### `testbidiSuccess.grpc`

Demonstrates an success example of equality test for the gRPC bidirectional stream
messages send and recieved. 
Those tests will pass in case of [grpcb.in](https://github.com/moul/pb/blob/master/hello/hello.proto) 
*hello.proto* test endpoint is alive.

The command will exit with 0 code in case of success.

### `testbidiFail.grpc`

Demonstares how the test fail when one of the recievied messages is not equal to
the expected one. 

This test will exit with code greater than 0.

## Check the exit code

To check the exit code you can run the `echo $?` command which shows the last command exit code.
