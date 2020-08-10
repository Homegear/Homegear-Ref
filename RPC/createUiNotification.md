<!---
{
    "category": "UI",
    "name": "createUiNotification",
    "shortDescription": "Creates a new UI notification"
}
--->

# Signatures

```
Integer createUiNotification(Struct notificationDescription)
```

# Description

This method creates a new UI notification and stores the provided `Struct` in Homegear's database. UI notifications are notifications that should be displayed in frontends. When this method is called, Homegear calls the event method [uiNotificationCreated](#uiNotificationCreated). Additionally all notifications can be retrieved by calling [getUiNotifications()](#getUiNotifications).

It is assumed that there is a page within the frontend for displaying notifications. Without any flags specified, the notification should only be displayed there. When the notification doesn't have buttons, there should be a way to remove the notification, e. g. by displaying a "remove" button which triggers a call to [removeUiNotification](#removeUiNotification).

When selecting an element within the notification list, an optional modal can be shown. The modal can have an arbitrary number of buttons. Pressing a button must call [uiNotificationAction](#uiNotificationAction). This triggers the associated action within Homegear. The action is user defined, i. e. in Node-BLUE or an IPC client. Pressing a button mustn't call [removeUiNotification](#removeUiNotification). Removing the notification should be handled within the user's custom logic in Homegear.

In addition to this default behaviour there are two more options:

1. The notification can be displayed as an overlay with or without buttons.
    * When there is a modal defined, selection the overlay should open the modal. No buttons should be displayed within the overlay itself in this case.
    * When there is no modal defined, buttons should be displayed within the overlay.
    * When there are no buttons defined, the overlay should be closeable another way (i. e. by displaying a "X" button).
2. The notification can be displayed as a modal that is shown regardless which frontend page is open. The user needs to interact with the modal in order to be able to use the frontend. This can be used for example to show terms and conditions.

# Parameters

## notificationDescription

The following fields are predefined by Homegear and should be used:

| Key | Mandatory | Type | Description |
|:---|:---|:---|:---|
| `type` | yes | `String` | An arbitrary type string to identify notifications of the same category. |
| `flags` | no | `Struct` | Modifiers defining how the notification should be displayed. |
| `flags/overlayNotification` | no | `Boolean` | Notification should be displayed as an overlay. |
| `flags/closeable` | no | `Boolean` | Only applicable when `overlayNotification` is `true`. Forces the overlay notification to be closable. |
| `flags/hasModal` | no | `Boolean` | When set, the notification has a modal. |
| `flags/overlayModal` | no | `Boolean` | Only applicable when `hasModal` is `true`. Forces the modal to be shown within the frontend. The user can't use the frontend without interacting with the modal first. |
| `title` | yes | `Struct` | A short text describing the notification. This title is shown in the notification list and within the overlay. The title must be provided for every supported language. Fallback language is `en-US`. |
| `modalTitle` | no | `Struct` | Only applicable when `hasModal` is `true`. This title is shown at the top of the modal. The title must be provided for every supported language. Fallback language is `en-US`. |
| `modalContent` | no | `Struct` | Only applicable when `hasModal` is `true`. This defines the modal content as `HTML`. The content must be provided for every supported language. Fallback language is `en-US`. |
| `buttons` | no | `Array<Struct>` | Defines buttons to interact with the notification. I. e. "yes" - "no" or "accept" - "decline". |
| `buttons/#/id` | no | `Integer` | The ID of the button starting with `0`. |
| `buttons/#/type` | no | `String` | This just defines a CSS class to use. E. g. "success", "warning", "error". |
| `buttons/#/reloadUi` | no | `Boolean` | The UI should be reloaded after selecting this button. |
| `buttons/#/closeModal` | no | `Boolean` | Pressing this button should close the modal. |
| `buttons/#/label` | no | `Struct` | The label of the button. It must be provided for every supported language. Fallback language is `en-US`. |
| `buttons/#/icon` | no | `String` | The icon or icon class to use. |

In addition to these fields, more data can be inserted into the `Struct`. Homegear returns the additional data as provided.

### Example

An example description might look like this:

```json
{
  "type": "my-notification-type",
  "flags": {
    "closeable": true,
    "hasModal": true,
    "overlayNotification": true,
    "overlayModal": false
  },
  "title": {
    "en-US": "Please do something",
    .
    .
    .
  },
  "modalTitle": {
    "en-US": "My Modal",
    .
    .
    .
  },
  "modalContent": {
    "en-US": "<p>My HTML</p>"
  },
  "buttons": [
    {
      "id": 0,
      "type": "success",
      "reloadUi": true,
      "closeModal": true,
      "label": {
        "en-US": "OK"
      },
      "icon": "my-icon",
      "my-data": [0, 1, 2, 3]
    },
    .
    .
    .
  ],
  "my-data": {"first": 0, "second": 1}
}
```

# Return Values

Returns the ID of the new notification on success.

# Exceptions

This method only throws default exceptions.