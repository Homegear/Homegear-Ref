<!---
{
    "category": "Rooms and Categories",
    "name": "updateBuildingPart",
    "shortDescription": "Updates the translations and metadata of an existing building part"
}
--->

# Signatures

```
Void updateBuildingPart(Integer buildingPartId, Struct translations, Struct metadata = {})
```

# Description

This method updates the translations and metadata of an existing building part.

# Parameters

## buildingPartId

The ID of the building part as returned by [createBuildingPart()](#createBuildingPart) or [getBuildingParts()](#getBuildingParts).

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

Returns `Void` on success.

| Code | Description            |
| :--- | :--------------------- |
| -1   | Unknown building part. |