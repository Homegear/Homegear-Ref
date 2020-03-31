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

Returns an `Array` with all variable profiles. Note that the profile ID is encoded in the key `id`, the language-specific profile name in the key `name`.

# Exceptions

This method only throws default exceptions.
