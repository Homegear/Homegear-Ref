<!---
{
    "category": "UI",
    "name": "getRoomUiElements",
    "shortDescription": "Returns all UI elements assigned to a room"
}
--->

# Signatures

```php
Array<Struct> getRoomUiElements(Integer room, String language)
```

# Description

This method returns all UI elements assigned to the specified room. The assigned room can be specifed in [addUiElement()](#addUiElement) by placing the room ID in the key `room`.

# Parameters

## room

The ID of the room to return UI elements for.

## language

The language to return the UI elements for. E. g. `en-US` or `de-DE`.

# Return Values

Returns an `Array` with all UI elements within the specified room.

# Exceptions

| Code | Description          |
|:-----|:---------------------|
| -1   | The room is unknown. |
