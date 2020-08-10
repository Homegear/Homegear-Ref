<!---
{
    "category": "Event Server - UI",
    "name": "uiNotificationCreated",
    "shortDescription": "Called when there is a new UI notification"
}
--->

# Signatures

```
Void uiNotificationCreated(Integer notificationId)
```

# Description

This method is called by Homegear when [createUiNotification](#createUiNotification) is called and the element has successfully been stored to database. To retrieve additional information, call [getUiNotification](#getUiNotification).


# Parameters

## notificationId

The ID of the new notification.

# Return Values

Returns `Void` on success.