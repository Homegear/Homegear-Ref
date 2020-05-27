<!---
{
    "category": "Devices",
    "name": "setValue",
    "shortDescription": "Sets the value of a device variable"
}
--->

# Signatures

```
Void setValue(Integer peerId, Integer channel, String variableName, Variant value [, Boolean wait = true])
```

# Deprecated Signatures

```
Void setValue(String address, String variableName, Variant value [, Boolean wait = true])
```

# Description

This method sets the value of a device variable. Note that it can't be used to set configuration parameters.

# Parameters

## peerId

The ID of the peer to set the value. Set `peerId` to `0` to set a system variable. When the system variable doesn't exist, it is created.

### Example

```json
31
```

## channel

The channel of the peer to set the value. Set `channel` to `-1` for system variables. When `peerId` is not `0` and `channel` is `-1`, `variableName` specifies a metadatum of the device. When the metadatum doesn't exist, it is created.

### Example

```json
3
```

## variableName

The name of the variable to set.

### Example

```json
"SETPOINT_TEMPERATURE"
```

## value

The new value of the variable. Please make sure the passed variable has the correct type (for languages with implied type conversion `21.0` for `Float` and not `21`). A type conversion is implemented, but you shouldn't rely on it. When the type of the variable is `Float` or `Integer`, instead of passing the actual new value, you can also pass the following operations, followed without space by a number. The type of the value needs to be `String`:

* `+=<Number>`
* `-=<Number>`
* `*=<Number>`
* `/=<Number>`

In addtition `!` toggles a Boolean value. This operation doesn't need to be followed by number.

You don't have to check for minimum or maximum values, as the new value will automatically be capped.

### Example

```json
31
```

### Example 2

```json
"+=0.5"
```

## wait

Set to `false` if you don't want to wait for a response from the device. By default Homegear waits for a response when possible and returns an error when there is none. In some device families setting `wait` to `false` has no effect.

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description                  |
|:-----|:-----------------------------|
| -2   | Peer or channel are unknown. |
| -5   | Unknown parameter.           |
| -6   | Parameter is readonly.       |
| -100 | No answer from device.       |
| -101 | Device returned error.       |