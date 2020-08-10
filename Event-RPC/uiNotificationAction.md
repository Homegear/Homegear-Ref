<!---
{
    "category": "Event Server - UI",
    "name": "uiNotificationAction",
    "shortDescription": "Called when a UI notification button is pressed"
}
--->

# Signatures

```
Void uiNotificationAction(Integer notificationId, String type, Integer buttonId)
```

# Description

This method is called by Homegear when [uiNotificationAction](#uiNotificationAction) is called and indicates a button press by the user.


# Parameters

## notificationId

The ID of the notification.

## type

The type of the notification as provided to [createUiNotification](#createUiNotification).

## buttonId

The ID of the button that was pressed.

# Return Values

Returns `Void` on success.