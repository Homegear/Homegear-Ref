<!---
{
    "category": "Variable Profiles",
    "name": "deleteVariableProfile",
    "shortDescription": "Deletes a variable profile (= \"scene\")"
}
--->

# Signatures

```
Void deleteVariableProfile(Integer profileId)
```

# Description

This method deletes a variable profile previously created using [addVariableProfile()](#addVariableProfile).

# Parameters

## profileId

The ID of the profile as returned by [addVariableProfile()](#addVariableProfile) or the key `id` of the get methods.

# Return Values

Returns `Void` on success.

# Exceptions

This method only throws default exceptions.