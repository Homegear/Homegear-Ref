<!---
{
    "category": "UI",
    "name": "getUiNotification",
    "shortDescription": "Returns a single UI notification"
}
--->

# Signatures

```
Struct getUiNotification(Integer notificationId, String languageCode)
```

# Description

This method returns a single UI notification previously created with [createUiNotification](#createUiNotification).

# Parameters

## notificationId

The ID of the notification.

## languageCode

The language code to return, e. g. `de-DE`. The fallback language code is `en-US`.

# Return Values

Returns an the notification description on success.

# Exceptions

| Code | Description                                     |
| :--- | :---------------------------------------------- |
| -1   | Returned when the UI notification is not found. |