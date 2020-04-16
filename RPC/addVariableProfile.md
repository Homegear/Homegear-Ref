<!---
{
    "category": "Variable Profiles",
    "name": "addVariableProfile",
    "shortDescription": "Adds an UI element to Homegear's UI (= \"scene\")"
}
--->

# Signatures

```
Integer addVariableProfile(Struct translations, Struct profile)
```

# Description

This method adds a variable profile to Homegear. A variable profile is a set of predefined variable states. It can be activated by calling [activateVariableProfile()](#activateVariableProfile). A profile can be assigned to a room.

# Parameters

## translations

A `Struct` with language/name pairs of the profile:

```json
{
    "en-US": "My profile",
    "de-DE": "Mein Profil"
}
```

## profile

The profile itself. The content of the profile `Struct` can be chosen freely. Only the key `values` containing the variable states to set is mandatory. `values` is an `Array`. Each element again is a `Struct` with the following mandatory elements:

### Mandatory elements of the `values` array

| Key        | Type      | Description                         |
|:-----------|:----------|:------------------------------------|
| `peerId`   | `Integer` | The peer ID of the variable to set. |
| `channel`  | `Integer` | The channel of the variable to set. |
| `variable` | `String`  | The name of the variable to set.    |
| `value`    | `Variant` | The value to set.                   |

### Optional elements of the `values` array

In addition there are the following optional elements:

| Key                      | Type      | Default | Description                                                                                                                                                      |
|:-------------------------|:----------|:--------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `wait`                   | `Boolean` | `false` | Wait for a value to be sent to the device before setting the next value.                                                                                         |
| `ignoreValueFromDevice`  | `Boolean` | `true`  | Ignore values from device for detection if a profile is currently active.                                                                                        |
| `deviceRefractoryPeriod` | `Integer` | `60`    | Only used when `ignoreValueFromDevice` is `false`. For this number of seconds values from the device are ignored for detection if a profile is currently active. |

### Optional elements of the profile struct

| Key    | Type      | Default | Description                                            |
|:-------|:----------|:--------|:-------------------------------------------------------|
| `room` | `Integer` |         | When specified the profile is associated to this room. |

### Example

```json
{
    "myOptionalKey": ["myOptionalArray"],
    "room": 12,
    "values": [
        {
            "peerId": 12,
            "channel": 1,
            "variable": "STATE",
            "value": true
        },
        {
            "peerId": 14,
            "channel": 2,
            "variable": "LEVEL",
            "value": 47
        }
    ]
}
```

# Return Values

Returns the ID of the newly created profile.

# Exceptions

| Code | Description                                                                        |
|:-----|:-----------------------------------------------------------------------------------|
| -1   | The parameters are invalid or the profile could not be inserted into the database. |

# Examples

```bash
homegear -e rc '
$hg->setSystemVariable("TEST1", false);
$hg->setSystemVariable("TEST2", 93);
$hg->setSystemVariable("TEST3", "Hello World");

$profileId = $hg->addVariableProfile([
    "en-US" => "My profile",
    "de-DE" => "Mein Profil"
], [
    "values" => [
        [
            "peerId" => 0,
            "channel" => -1,
            "variable" => "TEST1",
            "value" => true
        ],
        [
            "peerId" => 0,
            "channel" => -1,
            "variable" => "TEST2",
            "value" => 47
        ],
        [
            "peerId" => 0,
            "channel" => -1,
            "variable" => "TEST3",
            "value" => "Hello Homegear"
        ]
    ]
]);

$hg->activateVariableProfile($profileId);
print_v($hg->getSystemVariable("TEST1"));
print_v($hg->getSystemVariable("TEST2"));
print_v($hg->getSystemVariable("TEST3"));
'
```