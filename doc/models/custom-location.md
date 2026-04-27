
# Custom Location

Custom location details for a working location event.

*This model accepts additional fields of type array.*

## Structure

`CustomLocation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `label` | `?string` | Optional | Label for the custom location. | getLabel(): ?string | setLabel(?string label): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "label": "Home Office",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

