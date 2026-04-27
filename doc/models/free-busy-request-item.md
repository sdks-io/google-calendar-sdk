
# Free Busy Request Item

Identifies a calendar or group to include in a free/busy query.

*This model accepts additional fields of type array.*

## Structure

`FreeBusyRequestItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | The identifier of a calendar or a group. | getId(): string | setId(string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "id": "primary",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

