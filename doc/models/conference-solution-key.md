
# Conference Solution Key

Identifies a conference solution type.

*This model accepts additional fields of type array.*

## Structure

`ConferenceSolutionKey`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | The conference solution type (e.g. "hangoutsMeet", "eventHangout"). | getType(): ?string | setType(?string type): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "type": "hangoutsMeet",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

