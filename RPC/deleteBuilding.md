<!---
{
    "category": "Rooms and Categories",
    "name": "deleteBuilding",
    "shortDescription": "Deletes a building"
}
--->

# Signatures

```
Void deleteBuilding(Integer buildingId)
```

# Description

This method deletes a building.


# Parameters

## buildingId

The ID of the building as returned by [createBuilding()](#createBuilding) or [getBuildings()](#getBuildings).

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description       |
|:-----|:------------------|
| -1   | Unknown building. |