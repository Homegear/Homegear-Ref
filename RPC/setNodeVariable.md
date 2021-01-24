<!---
{
    "category": "Node-BLUE",
    "name": "setNodeVariable",
    "shortDescription": "Executes \"setNodeVariable\" in the specified node."
}
--->

# Signatures

```
Void setNodeVariable(String nodeId, String variableName, Variant value)
```

# Description

This method calls `setNodeVariable` in the specified node. For this to work, the node must implement `setNodeVariable`. The variable names and values are node-specific.

# Parameters

## nodeId

The node to call `setNodeVariable` in.

## variableName

The variable to set.

## value

The value to set the variable `variableName` to.

# Return Values

Returns `Void` on success:

# Exceptions

This method only throws default exceptions.

# Examples

```bash
homegear -e rc '$hg->setNodeVariable("fbda37e9.6b2ee8", "my-variable", true);'
```