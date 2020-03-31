<!---
{
    "category": "UI",
    "name": "checkUiElementSimpleCreation",
    "shortDescription": "Checks if automatic UI element creation is possible on a variable"
}
--->

# Signatures

```
Boolean checkUiElementSimpleCreation(Integer peerId, Integer channel, String variableName)
```

# Description

This method checks if simple UI element creation is supported by a variable. If it is possible, the variable can be visualized in an UI by calling [addUiElement()](#addUiElement) with `peerId`, `channel`, `variableName` and a `label` as parameters.

# Parameters

## peerId

The peer ID to check.

## channel

The channel to check.

## variableName

The variable name to check.

# Return Values

Returns `true` when simple UI element creation is possible and `false` otherwise.

# Exceptions

This method only throws default exceptions.

# Examples

```bash
homegear -e rc '$hg->setSystemVariable(0, -1, "TEST", true);'
homegear -e rc 'print_v($hg->checkUiElementSimpleCreation(0, -1, "TEST"));'
```