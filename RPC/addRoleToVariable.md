<!---
{
    "category": "Roles",
    "name": "addRoleToVariable",
    "shortDescription": "Adds a role to a variable"
}
--->

# Signatures

```
Boolean addRoleToVariable(Integer peerId, Integer channel, String variableName, Integer roleId [, Integer direction = 2 [, Boolean invert = false [, Struct scale = {}]]])
```

# Description

This method adds a role to a variable.

# Parameters

## peerId

The ID of the peer to add the role to. Set to `0` to add a role to a system variable.

### Example

```json
12
```

## channel

The channel of the peer to add the role to. Set to `-1` to add a role to a system or metadata variable.

### Example

```json
1
```

## variableName

The variable of the peer to add the role to.

### Example

```json
"TEMPERATURE"
```

## roleId

The ID of the role as returned by [createRole()](#createRole) or [getRoles()](#getRoles).

### Example

```json
201003
```

## invert

Invert the value of the variable. This makes the variable look like the inverted value everywhere it can be accessed.

## scale

Scales the logical value of the variable. This makes the variable look like the scaled version everywhere it can be accessed. Scale is a `Struct` with the following entries:

| Key | Optional | Description          |
|:-----|:--|:---------------------|
`valueMin` | yes | The minimum value of the unscaled variable. If omitted Homegear uses the minimum value from the device description file.
`valueMax` | yes | The maximum value of the unscaled variable. If omitted Homegear uses the maximum value from the device description file.
`scaleMin` | no | The minimum value of the scale range the variable should be scaled to.
`scaleMax` | no | The maximum value of the scale range the variable should be scaled to.

### Example

```json
{
	"valueMin": 0,
	"valueMax": 255,
	"scaleMin": 0,
	"scaleMax": 100
}
```

This will scale the device value to a value between `0` and `100`.

# Return Values

Returns `true` on success and `false` if something went wrong (e. g. unknown channel).

# Exceptions

| Code | Description          |
|:-----|:---------------------|
| -1   | Role unknown.        |
| -2   | Variable is unknown. |