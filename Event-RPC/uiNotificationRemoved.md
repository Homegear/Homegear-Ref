<!---
{
    "category": "Event Server - UI",
    "name": "uiNotificationRemoved",
    "shortDescription": "Called when a new UI notification has been removed"
}
--->

# Signatures

```
Void uiNotificationRemoved(Integer notificationId)
```

# Description

This method is called by Homegear when [removeUiNotification](#removeUiNotification) is called and the element has been removed from the database.


# Parameters

## notificationId

The ID of the removed notification.

# Return Values

Returns `Void` on success.