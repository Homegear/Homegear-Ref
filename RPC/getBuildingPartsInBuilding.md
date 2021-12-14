<!---
{
    "category": "Rooms and Categories",
    "name": "getBuildingPartsInBuilding",
    "shortDescription": "Returns all building parts of a building"
}
--->

# Signatures

```
Array<Integer> getBuildingPartsInBuilding(Integer buildingId)
```

# Description

This method returns all building parts of a building.

# Parameters

## buildingId

The ID of the building as returned by [createBuilding()](#createBuilding) or [getBuildings()](#getBuildings).

# Return Values

Returns an `Array<Integer>` with all building part IDs assigned to the specified building.

# Exceptions

| Code | Description       |
| :--- | :---------------- |
| -1   | Unknown building. |