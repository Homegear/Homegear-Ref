<!---
{
    "category": "UI",
    "name": "addUiElement",
    "shortDescription": "Adds an UI element to Homegear's UI"
}
--->

# Signatures

```
(1) Integer addUiElement(Integer peerId, Integer channel, String variableName, String label)
(2) Integer addUiElement(String elementId, Struct elementDescription [, Struct metadata = Void])
```

# Description

These methods add an UI element to a Homegear UI module. They work, even if no UI module is installed.

We call method `(1)` "simple UI element creation". For this signature to work, the variable needs an assigned role. Additionally the variable, channel or peer (checked in this order) needs to assigned to a room. Homegear then tries to match an UI element to the variable. The UI elements to match are defined in Homegear's roles, which are loaded by default from `defaultRoles.json`. If a UI element needs multiple variables, you can specify any variable in this method. The other variables are matched by role and room automatically.

Signature `(2)` is much more flexible than signature `(1)` but also much more complex. It doesn't need any role or room to be assigned to a variable. The UI element itself is matched my it's name (and is defined by default in XML files in `/etc/homegear/devices/uiBase`). Basically each UI element needs a list of input variables and output variables. So in addition to the UI element name these variables need to be defined. See the parameter descriptions for an example.

# Parameters

## peerId

The ID of the peer to add an UI element for.

## channel

The channel of the peer to add an UI element for.

## variable name

The name of the variable to add an UI element for.

## label

The label of the UI element which will be displayed in the UI.

## elementId

The ID (name) of the UI element as defined in it's XML file.

```json
"Base.lightingSwitch"
```

## elementDescription

A `Struct` to set label, room and input/output variables for the UI element.

### Example

```json
{
    "inputPeers": [
        [
            {
                "peer": 0,
                "channel": -1,
                "name": "LIGHT"
            }
        ]
    ],
    "outputPeers": [
        [
            {
                "peer": 0,
                "channel": -1,
                "name": "LIGHT"
            }
        ]
    ],
    "label": "My light",
    "room": 3
}
```

## metadata

Dynamic metadata which can be overwritten later with [setUiElementMetadata()](#setUiElementMetadata) and read with [getUiElementMetadata()](#getUiElementMetadata). It is returned in key `dynamicMetadata` in the `Struct` returned by [getAllUiElements()](#getAllUiElements) The dynamic metadata can also be set in `uiElementDescription` by specifying it in key `dynamicMetadata`. Specifying it in `metadata` takes precedence over `dynamicMetadata` in `elementDescription`.

# Return Values

Returns the database ID of the newly created UI element.

# Exceptions

| Code | Description                                                                                                                                                                                                               |
|:-----|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -1   | Returned when the input parameters are invalid or the element couldn't be added to the database. For signature `(1)` additionally when the variable couldn't be matched. The returned error string contains more detauls. |

# Examples

```bash
homegear -e rc '
//Create a new room
$roomId = $hg->createRoom(["en-US" => "Living room", "de-DE" => "Wohnzimmer"]);
//Create a new system variable
$hg->setSystemVariable("TEST", true);
//Assign room to system variable
$hg->addVariableToRoom(0, -1, "TEST", $roomId);
//Assign role "100001" (= Light - state) to system variable
$hg->addRoleToVariable(0, -1, "TEST", 100001);

//Add UI element by using simple UI element creation
$hg->addUiElement(0, -1, "TEST", "My light");
'
```