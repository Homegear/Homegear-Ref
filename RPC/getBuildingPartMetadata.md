<!---
{
    "category": "Rooms and Categories",
    "name": "getBuildingPartMetadata",
    "shortDescription": "Returns the metadata of an existing building part"
}
--->

# Signatures

```
Struct getBuildingPartMetadata(Integer buildingPartId)
```

# Description

This method returns the metadata of an existing building part.

# Parameters

## buildingPartId

The ID of the building part as returned by [createBuildingPart()](#createBuildingPart) or [getBuildingParts()](#getBuildingParts).

# Return Values

Returns the buildings part's metadata on success.

# Exceptions

| Code | Description            |
| :--- | :--------------------- |
| -1   | Unknown building part. |