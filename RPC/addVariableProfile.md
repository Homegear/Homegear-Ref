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

The profile itself. The content of the `Struct` can be chosen freely. Only the key `values` containing the variable states to set is mandatory. `values` is an `Array`. Each element again is an `Array` of four or five elements:

| Number of elements | Description                                                                                                                                                                                                                                                                               |
|:-------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 4 elements         | Peer ID (`Integer`), channel (`Integer`), variable name (`String`) and variable value (`Variant`).                                                                                                                                                                                        |
| 5 elements         | Peer ID (`Integer`), channel (`Integer`), variable name (`String`), variable value (`Variant`) and "wait" (`Boolean`). The last parameter specifies if the profile execution waits for the parameter to be set. By default the execution doesn't wait (last parameter is set to `false`). |

The room ID can be optionally specified in `room`.

### Example

```json
{
    "myOptionalKey": ["myOptionalArray"],
    "room": 12,
    "values": [
        [12, 1, "STATE", true],
        [14, 2, "LEVEL", 47]
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
        [0, -1, "TEST1", true],
        [0, -1, "TEST2", 47],
        [0, -1, "TEST3", "Hello Homegear"]
    ]
]);

$hg->activateVariableProfile($profileId);
print_v($hg->getSystemVariable("TEST1"));
print_v($hg->getSystemVariable("TEST2"));
print_v($hg->getSystemVariable("TEST3"));
'
```