
# Conference Solution

Conference solution information, such as Google Meet.

*This model accepts additional fields of type array.*

## Structure

`ConferenceSolution`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `key` | [`?ConferenceSolutionKey`](../../doc/models/conference-solution-key.md) | Optional | Identifies a conference solution type. | getKey(): ?ConferenceSolutionKey | setKey(?ConferenceSolutionKey key): void |
| `name` | `?string` | Optional | User-visible name of the conference solution. | getName(): ?string | setName(?string name): void |
| `iconUri` | `?string` | Optional | User-visible icon for this solution. | getIconUri(): ?string | setIconUri(?string iconUri): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "name": "Google Meet",
  "iconUri": "https://example.com",
  "key": {
    "type": "type0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

