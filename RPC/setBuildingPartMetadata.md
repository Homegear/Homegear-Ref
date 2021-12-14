<!---
{
    "category": "Rooms and Categories",
    "name": "setBuildingPartMetadata",
    "shortDescription": "Sets the metadata of an existing building part"
}
--->

# Signatures

```
Void setBuildingPartMetadata(Integer buildingPartId, Struct metadata)
```

# Description

This method updates the metadata of an existing building part.

# Parameters

## buildingPartId

The ID of the building part as returned by [createBuildingPart()](#createBuildingPart) or [getBuildingParts()](#getBuildingParts).

## metadata

Arbitrary metadata.

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description            |
| :--- | :--------------------- |
| -1   | Unknown building part. |