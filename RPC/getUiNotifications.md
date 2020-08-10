<!---
{
    "category": "UI",
    "name": "getUiNotifications",
    "shortDescription": "Returns all UI notifications"
}
--->

# Signatures

```
Array<Struct> getUiNotifications(String languageCode)
```

# Description

This method returns all UI notifications previously created with [createUiNotification](#createUiNotification).

# Parameters

## languageCode

The language code to return, e. g. `de-DE`. The fallback language code is `en-US`.

# Return Values

Returns an array with all notification descriptions on success.

# Exceptions

This method only throws default exceptions.