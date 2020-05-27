<!---
{
    "category": "Rooms and Categories",
    "name": "updateBuilding",
    "shortDescription": "Updates the translations and metadata of an existing building"
}
--->

# Signatures

```
Void updateBuilding(Integer buildingId, Struct translations, Struct metadata = {})
```

# Description

This method updates the translations and metadata of an existing building.

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

Returns `Void` on success.

| Code | Description       |
|:-----|:------------------|
| -1   | Unknown building. |