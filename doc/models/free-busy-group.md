
# Free Busy Group

Expansion result for a single group.

*This model accepts additional fields of type array.*

## Structure

`FreeBusyGroup`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `calendars` | `?(string[])` | Optional | List of calendars that are members of this group. | getCalendars(): ?array | setCalendars(?array calendars): void |
| `errors` | [`?(FreeBusyError[])`](../../doc/models/free-busy-error.md) | Optional | Optional errors for this group. | getErrors(): ?array | setErrors(?array errors): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "calendars": [
    "calendars1",
    "calendars2"
  ],
  "errors": [
    {
      "domain": "domain6",
      "reason": "reason4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "domain": "domain6",
      "reason": "reason4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "domain": "domain6",
      "reason": "reason4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

