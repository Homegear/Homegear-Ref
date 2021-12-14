<!---
{
    "category": "General",
    "name": "getServiceMessages",
    "shortDescription": "Returns all service messages"
}
--->

# Signatures

```
(1) Array<Struct> getServiceMessages(Boolean newFormat, String language)
(2) Array<Array> getServiceMessages(Boolean newFormat, String language)
```

# Description

This method returns all service messages that are currently active in Homegear (device unreachable, config pending, low battery, sabotage, ...).

Signature `(1)` is returned when `newFormat` is set to `true`. Signature `(2)` is returned, when it is set to `false`.

# Parameters

## newFormat

Recommended. If `true`, Homegear returns the peer ID instead of the serial number, global and family service messages and more information. By default, the deprecated old format is returned for compatibility reasons.

## language

The language to return service messages for. E. g. `en`, `en-US` or `de-DE`.

# Return Values

This methon returns an `Array`, and each element in the `Array` is a service message.
If `newFormat` is `true`, each element is a `Struct` with the following elements:

| Key             | Type      | Types         | Optional | Description                                                  |
| --------------- | --------- | ------------- | -------- | ------------------------------------------------------------ |
| `TYPE`          | `Integer` |               | no       | `0` for global, `1` for family and `2` for device service messages. |
| `PRIORITY`      | `Integer` | `0`, `1`, `2` | no       | `1`: critical, `2`: error, `3`: warning, `4`: info, `5`: debug |
| `TIMESTAMP`     | `Integer` | `0`, `1`, `2` | no       | The unix timestamp in seconds of the timepoint the service message was set. |
| `FAMILY_ID`     | `Integer` | `1`           | no       | The ID of the family that created the service message.       |
| `INTERFACE`     | `String`  | `1`           | yes      | When the service message is associated to a communication interface, the interface ID is set here. |
| `PEER_ID`       | `Integer` | `2`           | no       | The ID of the peer that created the service message.         |
| `CHANNEL`       | `Integer` | `2`           | no       | The channel the service message is associated with.          |
| `VARIABLE`      | `String`  | `2`           | no       | The variable the service message is associated with.         |
| `MESSAGE_ID`    | `Integer` | `0`, `1`      | no       | An message ID to identify the service message. The combination of `MESSAGE_ID` and `MESSAGE_SUBID` is unique. |
| `MESSAGE_SUBID` | `String`  | `0`, `1`      | no       | A sub ID to indentify the service message. The combination of `MESSAGE_ID` and `MESSAGE_SUBID` is unique. |
| `MESSAGE`       | `String`  | `0`, `1`, `2` | no       | The translated service message. If `language` is not specified, a Struct with all translations is returned. If a service message can be set multiple times (e. g. communication module service messages), a unique identifier is appended separated by a `.` (dot). |
| `DATA`          | `Variant` | `0`, `1`      | yes      | Additional data associated with the service message.         |
| `VALUE`         | `Boolean` | `0`, `1`, `2` | no       | The value of the service message.                            |

If `newFormat` is `false` or not set, the depracated old format is returned.

# Exceptions

| Code | Description          |
|:-----|:---------------------|
| -1   | The room is unknown. |
