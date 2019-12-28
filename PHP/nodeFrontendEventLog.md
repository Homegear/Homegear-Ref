<!---
{
    "category": "Nodes",
    "name": "HomegearNodeBase::frontendEventLog",
    "shortDescription": "Writes a line to the Node-BLUE event log"
}
--->

# Signatures

```php
void frontendEventLog(string $message)
```


# Description

Write a line to the Node-BLUE event log. Please note that this log is not persistent. It only is written when Node-BLUE is open and connected in a browser.


# Parameters

## $message

The message to write to the log.


# Return Values

No value is returned.


# Examples

```php
frontendEventLog('My message to Node-BLUE.');
```