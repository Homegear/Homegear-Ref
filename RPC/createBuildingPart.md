<!---
{
    "category": "Rooms and Categories",
    "name": "createBuildingPart",
    "shortDescription": "Creates a new building part"
}
--->

# Signatures

```
Integer createBuildingPart(Struct translations, Struct metadata = {})
```

# Description

This method creates a new building part.


# Parameters

## translations

The name of the building part in different languages. The keys are the lower case ISO 639-1 language codes and the upper case ISO 3166-1 alpha-2 country codes seperated by a dash (e. g. en-US or fr-FR). The values are the building part names in the different languages.

### Example

```json
{
	"en-US": "Apartment 1",
	"de-DE": "Wohnung 1"
}
```

## metadata

Arbitrary metadata.

# Return Values

Returns the ID of the new building part on success.
