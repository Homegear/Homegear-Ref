<!---
{
    "category": "UI",
    "name": "removeUiElement",
    "shortDescription": "Sets metadata of an UI element"
}
--->

# Signatures

```
Void removeUiElement(Integer databaseId)
```

# Description

Deletes an UI element previously created with [addUiElement()](#addUiElement).

# Parameters

## databaseId

The ID of the UI element as returned by the get methods in the key `databaseId`.

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description                                |
|:-----|:-------------------------------------------|
| -1   | Returned when the database ID is invalid.  |
| -2   | Returned when the UI element is not found. |