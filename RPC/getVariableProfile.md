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

Returns the specified variable profile `Struct`. Note that the profile ID is encoded in the key `id`, the language-specific profile name in the key `name`.

# Exceptions

| Code | Description                |
|:-----|:---------------------------|
| -1   | The profile ID is unknown. |
