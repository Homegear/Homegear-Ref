<!---
{
    "category": "UI",
    "name": "setUiElementMetadata",
    "shortDescription": "Sets metadata of an UI element"
}
--->

# Signatures

```
Void setUiElementMetadata(Integer databaseId, Struct metadata)
```

# Description

Updates the metadata stored for an UI element previously created with [addUiElement()](#addUiElement). It can be read again with [getAllUiElements()](#getAllUiElements) (placed in the key `dynamicMetadata`) or with [getUiElementMetadata()](#getUiElementMetadata).

# Parameters

## databaseId

The ID of the UI element as returned by the get methods in the key `databaseId`.

## metadata

The metadata to set.

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description                                |
|:-----|:-------------------------------------------|
| -1   | Returned when the UI element is not found. |