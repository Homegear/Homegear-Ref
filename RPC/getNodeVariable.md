<!---
{
    "category": "Node-BLUE",
    "name": "getNodeVariable",
    "shortDescription": "Executes \"getNodeVariable\" in the specified node."
}
--->

# Signatures

```
Variant getNodeVariable(String nodeId, String variableName, Variant value)
```

# Description

This method calls `getNodeVariable` in the specified node. For this to work, the node must implement `getNodeVariable`. The variable names and values are node-specific.

# Parameters

## nodeId

The node to call `getNodeVariable` in.

## variableName

The variable to get.

# Return Values

Returns the value of the variable `variableName` on success.

# Exceptions

This method only throws default exceptions. The node is allowed to implement it's own exceptions though.

# Examples

```bash
homegear -e rc '$hg->getNodeVariable("fbda37e9.6b2ee8", "my-variable");'
```