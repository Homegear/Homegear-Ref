<!---
{
    "category": "Variable Profiles",
    "name": "getVariableProfile",
    "shortDescription": "Returns a single variable profile (= \"scene\")"
}
--->

# Signatures

```
Struct getVariableProfile(Integer profileId, String language)
```

# Description

This method returns a single variable profile previously created with [addVariableProfile()](#addVariableProfile).

# Parameters

## profileId

The ID of the profile as returned by [addVariableProfile()](#addVariableProfile) or [getAllVariableProfiles()](#getAllVariableProfiles).

## language

The language to fill the key name of the returned `Struct` with. E. g. `en-US` or `de-DE`.

# Return Values

Returns the specified variable profile `Struct`. The following keys are inserted by Homegear in addition to the content specified in [addVariableProfile()](#addVariableProfile):

| Key                   | Type      | Description                                                                     |
|:----------------------|:----------|:--------------------------------------------------------------------------------|
| `id`                  | `Integer` | The ID of the profile.                                                          |
| `name`                | `String`  | The language-specific profile name.                                             |
| `isActive`            | `Boolean` | `true` when the profile is currently active.                                    |
| `totalVariableCount`  | `Integer` | The total number of variables in this profile.                                  |
| `activeVariableCount` | `Integer` | The number of variables specified in this profile that match the profile value. |

# Exceptions

| Code | Description                |
|:-----|:---------------------------|
| -1   | The profile ID is unknown. |
