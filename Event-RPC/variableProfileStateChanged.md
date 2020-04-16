<!---
{
    "category": "Event Server - Variable Profiles",
    "name": "variableProfileStateChanged",
    "shortDescription": "Called when a variable profile changes it's state"
}
--->

# Signatures

```
Void variableProfileStateChanged(Integer profileId, Boolean state)
```

# Description

This method is called when a variable profile changes it's state to active or inactive. Active means that the variable values specified in the profile match the current values of the variables.


# Parameters

## profileId

The ID of the profile.

## state

The current state of the profile. `true` for active and `false` for inactive.

# Return Values

Returns `Void` on success.
