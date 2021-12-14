<!---
{
    "category": "Rooms and Categories",
    "name": "deleteBuildingPart",
    "shortDescription": "Deletes a building part"
}
--->

# Signatures

```
Void deleteBuildingPart(Integer buildingId)
```

# Description

This method deletes a building part.


# Parameters

## buildingPartId

The ID of the building part as returned by [createBuildingPart()](#createBuildingPart) or [getBuildingParts()](#getBuildingParts).

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description            |
| :--- | :--------------------- |
| -1   | Unknown building part. |