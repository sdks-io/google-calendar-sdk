
# Person

Identifies a person associated with the event, such as the creator or organizer.

*This model accepts additional fields of type array.*

## Structure

`Person`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The person's Profile ID. | getId(): ?string | setId(?string id): void |
| `email` | `?string` | Optional | The person's email address. | getEmail(): ?string | setEmail(?string email): void |
| `displayName` | `?string` | Optional | The person's name. | getDisplayName(): ?string | setDisplayName(?string displayName): void |
| `self` | `?bool` | Optional | Whether this person corresponds to the calendar owner. | getSelf(): ?bool | setSelf(?bool self): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "id": "abc123",
  "email": "user@example.com",
  "displayName": "Google Meet",
  "self": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

