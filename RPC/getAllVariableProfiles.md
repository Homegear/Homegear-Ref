<!---
{
    "category": "Variable Profiles",
    "name": "getAllVariableProfiles",
    "shortDescription": "Returns all variable profiles (= \"scenes\")"
}
--->

# Signatures

```
Array<Struct> getAllVariableProfiles(String language)
```

# Description

This method returns all variable profiles previously created with [addVariableProfile()](#addVariableProfile).

# Parameters

## language

The language to fill the key name of the returned `Struct` with. E. g. `en-US` or `de-DE`.

# Return Values

Returns an `Array` with all variable profiles. The following keys are inserted by Homegear in addition to the content specified in [addVariableProfile()](#addVariableProfile):

| Key                   | Type      | Description                                                                     |
|:----------------------|:----------|:--------------------------------------------------------------------------------|
| `id`                  | `Integer` | The ID of the profile.                                                          |
| `name`                | `String`  | The language-specific profile name.                                             |
| `isActive`            | `Boolean` | `true` when the profile is currently active.                                    |
| `totalVariableCount`  | `Integer` | The total number of variables in this profile.                                  |
| `activeVariableCount` | `Integer` | The number of variables specified in this profile that match the profile value. |

# Exceptions

This method only throws default exceptions.
