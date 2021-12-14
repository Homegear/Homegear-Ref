<!---
{
    "category": "Rooms and Categories",
    "name": "addBuildingPartToBuilding",
    "shortDescription": "Assigns a building part to a building"
}
--->

# Signatures

```
Boolean addBuildingPartToBuilding(Integer buildingId, Integer buildingPartId)
```

# Description

This method assigns a building part to a building.


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