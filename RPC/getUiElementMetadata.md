<!---
{
    "category": "UI",
    "name": "getUiElementMetadata",
    "shortDescription": "Gets metadata of an UI element"
}
--->

# Signatures

```
Struct getUiElementMetadata(Integer databaseId)
```

# Description

Returns metadata previously stored with [addUiElement()](#addUiElement) or [setUiElementMetadata()](#setUiElementMetadata).

# Parameters

## databaseId

The ID of the UI element as returned by the get methods in the key `databaseId`.

# Return Values

Returns the metadata `Struct`.

# Exceptions

| Code | Description                                |
|:-----|:-------------------------------------------|
| -1   | Returned when the UI element is not found. |
