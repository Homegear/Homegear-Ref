<!---
{
    "category": "UI",
    "name": "uiNotificationAction",
    "shortDescription": "Trigger a UI notification button action"
}
--->

# Signatures

```
Void uiNotificationAction(Integer notificationId, Integer buttonId)
```

# Description

This method should be called by the UI when a UI notification button is pressed by the user. When this method is called, Homegear calls the event method [uiNotificationAction](#uiNotificationActionEvent). This event method can be catched in Homegear's script engine, an IPC client or Node-BLUE to trigger an action and remove the notification when done.

# Parameters

## notificationId

The ID of the notification.

## buttonId

The ID of the button that was pressed..

# Return Values

Returns `Void` on success.

# Exceptions

| Code | Description                                     |
| :--- | :---------------------------------------------- |
| -1   | Returned when the UI notification is not found. |