<!---
{
    "category": "Rooms and Categories",
    "name": "setBuildingMetadata",
    "shortDescription": "Sets the metadata of an existing building"
}
--->

# Signatures

```
Void setBuildingMetadata(Integer buildingId, Struct metadata)
```

# Description

This method updates the metadata of an existing building.

# Parameters

## buildingId

The ID of the building as returned by [createBuilding()](#createBuilding) or [getBuildings()](#getBuildings).

## metadata

Arbitrary metadata.

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description       |
|:-----|:------------------|
| -1   | Unknown building. |