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

This method updates a variable profile previously created with [addVariableProfile()](#addVariableProfile). If an empty `Struct` is passed to `translations` or `profile`, this parameter is not updated. Like this it is possible to only update the profile or the translations. After adding variables to a role or removing variables from a role, all profiles with this role need to be updated. This can be done by restarting Homegear or by calling this method with `translations` and `profile` being an empty `Struct`.

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
