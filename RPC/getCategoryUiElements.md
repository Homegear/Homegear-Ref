<!---
{
    "category": "UI",
    "name": "getCategoryUiElements",
    "shortDescription": "Returns all UI elements assigned to a category"
}
--->

# Signatures

```php
Array<Struct> getCategoryUiElements(Integer category, String language)
```

# Description

This method returns all UI elements assigned to the specified category. The assigned categories can be specifed in [addUiElement()](#addUiElement) by placing an `Array` with category IDs in the key `categories`.

# Parameters

## category

The ID of the category to return UI elements for.

## language

The language to return the UI elements for. E. g. `en-US` or `de-DE`.

# Return Values

Returns an `Array` with all UI elements within the specified category.

# Exceptions

| Code | Description              |
|:-----|:-------------------------|
| -1   | The category is unknown. |
