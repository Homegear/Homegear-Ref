<!---
{
    "category": "Rooms and Categories",
    "name": "getRooms",
    "shortDescription": "Returns information about all rooms"
}
--->

# Signatures

```
Array<Struct> getRooms(String languageCode = "")
```

# Description

This method returns all room IDs, one or all translations and the room metadata.

# Parameters

## languageCode

An optional lower case ISO 639-1 language and upper case ISO 3166-1 alpha-2 country code seperated by a dash. If specified, only this translation is returned.

### Example

```json
"en-US"
```

# Return Values

Returns an `Array<Struct>` with all rooms on success. When `languageCode` is specified, each `Array` element is a `Struct` with three entries:

| Key  | Type      |
|:-----|:----------|
| `ID` | `Integer` |
| `NAME` | `String` |
| `METADATA` | `Struct` |

The name will be resolved in the following order:

1. `languageCode`
2. `en-US`
3. First available language
4. Empty string

When `languageCode` is not specified, each `Array` element is also a `Struct` with three entries:

| Key  | Type      |
|:-----|:----------|
| `ID` | `Integer` |
| `TRANSLATIONS` | `Struct` |
| `METADATA` | `Struct` |

The key of `TRANSLATIONS` is the language code and the value the translation.