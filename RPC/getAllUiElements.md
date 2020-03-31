<!---
{
    "category": "UI",
    "name": "getAllUiElements",
    "shortDescription": "Returns all UI elements"
}
--->

# Signatures

```
Array<Struct> getAllUiElements(String language)
```

# Description

This method returns all UI elements previously created with [addUiElement()](#addUiElement).

# Parameters

## language

The language to return the UI elements for. E. g. `en-US` or `de-DE`.

# Return Values

Returns an `Array` with all UI elements. Note that the database ID is encoded in the key `databaseId`.

# Exceptions

This method only throws default exceptions.
