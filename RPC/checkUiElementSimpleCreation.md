<!---
{
    "category": "UI",
    "name": "checkUiElementSimpleCreation",
    "shortDescription": "Checks if automatic UI element creation is possible on a variable"
}
--->

# Signatures

```
Struct checkUiElementSimpleCreation(Integer peerId, Integer channel, String variableName)
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

Returns a `Struct` with the following elements:

| Key          | Optional | Type             | Description                                                                                              |
|:-------------|:---------|:-----------------|:---------------------------------------------------------------------------------------------------------|
| visualizable | no       | `Boolean`        | Set to `true` when the variable can be visualized using simple UI element creation.                      |
| reason       | yes      | `String`         | Only set when `visualizable` is `false`. Explains why the variable is not visualizable.                  |
| visualized   | yes      | `Boolean`        | Only set when `visualizable` is `true`. Set to `true` when the variable is already used in a UI element. |
| uiElements   | yes      | `Array<Integer>` | UI elements that visualize this variable.                                                                |

# Exceptions

This method only throws default exceptions.

# Examples

```bash
homegear -e rc '$hg->setSystemVariable(0, -1, "TEST", true);'
homegear -e rc 'print_v($hg->checkUiElementSimpleCreation(0, -1, "TEST"));'
```