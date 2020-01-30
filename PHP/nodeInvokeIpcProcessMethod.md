<!---
{
    "category": "Nodes",
    "name": "HomegearNodeBase::invokeIpcProcessMethod",
    "shortDescription": "Executes a RPC method of a specific process connected over IPC."
}
--->

# Signatures

```php
variant invokeIpcProcessMethod(int $processId, string $methodName, array $parameters)
```


# Description

Executes a RPC method on a specific process connected using Homegear's IPC interface. I. e. you can start a new process from a node, let this process connect over the IPC interface and then call RPC methods on it.

This method is used for example by Homegear's Python node.


# Parameters

## $processId

The ID of the process to execute the RPC method in.


## $methodName

The name of the RPC method.


## $parameters

The parameters.


# Return Values

Returns the return value of the RPC call.


# Examples

```php
print_v(invokeIpcProcessMethod(5484, 'myRpcMethod, array('My 1st parameter', 2)));
```