<!---
{
    "category": "UI",
    "name": "removeUiNotification",
    "shortDescription": "Removes an UI notification"
}
--->

# Signatures

```
Void removeUiNotification(Integer notificationId)
```

# Description

This method removes a UI notification previously created with [createUiNotification](#createUiNotification). When this method is called, Homegear calls the event method [uiNotificationRemoved](#uiNotificationRemoved).

# Parameters

## notificationId

The ID of the notification to remove.

# Return Values

Returns `Void` on success.

# Exceptions

This method only throws default exceptions.