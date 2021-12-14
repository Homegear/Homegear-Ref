<!---
{
    "category": "Rooms and Categories",
    "name": "removeStoryFromBuilding",
    "shortDescription": "Removes a story from a building"
}
--->

# Signatures

```
Boolean removeStoryFromBuilding(Integer buildingId, Integer storyId)
```

# Description

This method removes a story from a building.

# Parameters

## buildingId

The ID of the building as returned by [createBuilding()](#createBuilding) or [getBuildings()](#getBuildings).

## storyId

The ID of the story as returned by [createStory()](#createStory) or [getStories()](#getStories).

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description       |
|:-----|:------------------|
| -1   | Unknown building. |
| -2   | Unknown story.    |