<!---
{
    "category": "Rooms and Categories",
    "name": "getStoriesInBuilding",
    "shortDescription": "Returns all stories of a building"
}
--->

# Signatures

```
Array<Integer> getStoriesInBuilding(Integer buildingId)
```

# Description

This method returns all stories of a building.

# Parameters

## buildingId

The ID of the building as returned by [createBuilding()](#createBuilding) or [getBuildings()](#getBuildings).

# Return Values

Returns an `Array<Integer>` with all story IDs assigned to the specified building.

# Exceptions

| Code | Description       |
|:-----|:------------------|
| -1   | Unknown building. |