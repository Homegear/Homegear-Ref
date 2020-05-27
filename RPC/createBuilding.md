<!---
{
    "category": "Rooms and Categories",
    "name": "createBuilding",
    "shortDescription": "Creates a new building"
}
--->

# Signatures

```
Integer createBuilding(Struct translations, Struct metadata = {})
```

# Description

This method creates a new building.


# Parameters

## translations

The name of the building in different languages. The keys are the lower case ISO 639-1 language codes and the upper case ISO 3166-1 alpha-2 country codes seperated by a dash (e. g. en-US or fr-FR). The values are the building names in the different languages.

### Example

```json
{
	"en-US": "Building 1",
	"de-DE": "Gebäude 1"
}
```

## metadata

Arbitrary metadata.

# Return Values

Returns the ID of the new building on success.
