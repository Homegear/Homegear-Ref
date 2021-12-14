<!---
{
    "category": "Rooms and Categories",
    "name": "addStoryToBuilding",
    "shortDescription": "Assigns a story to a building"
}
--->

# Signatures

```
Boolean addStoryToBuilding(Integer buildingId, Integer storyId)
```

# Description

This method assigns a story to a building.


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