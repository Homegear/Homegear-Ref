<!---
{
    "category": "Rooms and Categories",
    "name": "removeBuildingPartFromBuilding",
    "shortDescription": "Removes a building part from a building"
}
--->

# Signatures

```
Boolean removeBuildingPartFromBuilding(Integer buildingId, Integer buildingPartId)
```

# Description

This method removes a building part from a building.

# Parameters

## buildingId

The ID of the building as returned by [createBuilding()](#createBuilding) or [getBuildings()](#getBuildings).

## buildingPartId

The ID of the building part as returned by [createBuildingPart()](#createBuildingPart) or [getBuildingParts()](#getBuildingParts).

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description            |
| :--- | :--------------------- |
| -1   | Unknown building.      |
| -2   | Unknown building part. |