<!---
{
    "category": "UI",
    "name": "requestUiRefresh",
    "shortDescription": "Requests the UI to be reloaded"
}
--->

# Signatures

```
Void requestUiRefresh(String id)
```

# Description

This method should cause a Homegear UI to reload and triggers the event method [requestUiRefresh()](#requestUiRefreshEvent).


# Parameters

## id

An arbitrary ID which is passed to [requestUiRefresh()](#requestUiRefreshEvent). It can be used to identify a specific UI. When empty, all UIs should be refreshed.

# Return Values

Returns `Void` on success.
