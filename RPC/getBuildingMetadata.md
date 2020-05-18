<!---
{
    "category": "Rooms and Categories",
    "name": "getBuildingMetadata",
    "shortDescription": "Returns the metadata of an existing building"
}
--->

# Signatures

```
Struct getBuildingMetadata(Integer buildingId)
```

# Description

This method returns the metadata of an existing building.

# Parameters

## buildingId

The ID of the building as returned by [createBuilding()](#createBuilding) or [getBuildings()](#getBuildings).

# Return Values

Returns the buildings's metadata on success.

# Exceptions

| Code | Description       |
|:-----|:------------------|
| -1   | Unknown building. |