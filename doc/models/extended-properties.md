
# Extended Properties

Extended properties of the event.

*This model accepts additional fields of type array.*

## Structure

`ExtendedProperties`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `private` | `?array<string,string>` | Optional | Properties that are private to the copy of the event that appears on this calendar. | getPrivate(): ?array | setPrivate(?array private): void |
| `shared` | `?array<string,string>` | Optional | Properties that are shared between copies of the event on other attendees' calendars. | getShared(): ?array | setShared(?array shared): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "private": {
    "key0": "private0",
    "key1": "private1"
  },
  "shared": {
    "key0": "shared0",
    "key1": "shared9",
    "key2": "shared8"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

