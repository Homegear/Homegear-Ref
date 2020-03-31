<!---
{
    "category": "Variable Profiles",
    "name": "updateVariableProfile",
    "shortDescription": "Updates an existing variable profile (= \"scene\")"
}
--->

# Signatures

```
Struct updateVariableProfile(Integer profileId, Struct translations, Struct profile)
```

# Description

This method updates a variable profile previously created with [addVariableProfile()](#addVariableProfile). If an empty `Struct` is passed to `translations` or `profile`, the parameter is not updated. Like this it is possible to only update the profile or the translations.

# Parameters

## profileId

The ID of the profile as returned by [addVariableProfile()](#addVariableProfile) or the key `id` of the get methods.

## translations

See [addVariableProfile()](#addVariableProfile).

## profile

See [addVariableProfile()](#addVariableProfile).

# Return Values

Returns `true` on success and `false` on errors.

# Exceptions

| Code | Description                |
|:-----|:---------------------------|
| -1   | The profile ID is unknown. |
