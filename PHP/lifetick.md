<!---
{
    "category": "General",
    "name": "lifetick",
    "shortDescription": "Checks the state of all essential Homegear components."
}
--->

# Signatures

```php
bool lifetick()
```


# Description

This method checks all essential Homegear components. The components are:

## All RPC servers

Checks for hanging RPC method calls.


## The RPC client

Checks for hanging event broadcasts.


## All family modules

Executes `lifetick()` of each family module. There is a default implementation and families can implement their own lifetick.


## The script engine server

Checks for deadlocks in the communication with script engine clients.


## All script engine clients

Checks if the RPC method processing backlog is getting too large. Currently it returns `false` if there are more than 1000 items in one of the queues.


## The Node-BLUE server

Checks for deadlocks in the communication with Node-BLUE clients.


## All Node-BLUE clients

Checks if the node event and RPC method processing backlog is getting too large. Currently it returns `false` if there are more than 1000 items in one of the queues.


## The IPC server

Checks for deadlocks in the communication with IPC clients.


# Parameters

This method has no parameters.


# Return Values

Returns `true` if all components are ok and `false` if at least one component is not ok.


# Examples

```php
print_v($hg->lifetick());
```