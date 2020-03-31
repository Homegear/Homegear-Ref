<!---
{
    "category": "Variable Profiles",
    "name": "activateVariableProfile",
    "shortDescription": "Activates a variable profile (= \"scene\")"
}
--->

# Signatures

```
Boolean activateVariableProfile(Integer profileId)
```

# Description

This method activates a variable profile previously created using [addVariableProfile()](#addVariableProfile).

# Parameters

## profileId

The ID of the profile as returned by [addVariableProfile()](#addVariableProfile) or the key `id` of the get methods.

# Return Values

Returns `true` on success and `false` on errors.

# Exceptions

| Code | Description                |
|:-----|:---------------------------|
| -1   | The profile ID is unknown. |

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