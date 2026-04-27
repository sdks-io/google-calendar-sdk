
# Time Period

A time range representing a busy period.

*This model accepts additional fields of type array.*

## Structure

`TimePeriod`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `start` | `?DateTime` | Optional | The start of the busy time period (inclusive). | getStart(): ?\DateTime | setStart(?\DateTime start): void |
| `end` | `?DateTime` | Optional | The end of the busy time period (exclusive). | getEnd(): ?\DateTime | setEnd(?\DateTime end): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "start": "01/15/2024 09:00:00",
  "end": "01/15/2024 09:00:00",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

