
# Birthday Properties

Birthday or special event data. Used if eventType is birthday.

*This model accepts additional fields of type array.*

## Structure

`BirthdayProperties`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `contact` | `?string` | Optional | Resource name of the contact this birthday event is linked to. | getContact(): ?string | setContact(?string contact): void |
| `type` | [`?string(BirthdayType)`](../../doc/models/birthday-type.md) | Optional | Type of birthday or special event. | getType(): ?string | setType(?string type): void |
| `customTypeName` | `?string` | Optional | Custom type label if type is "custom". | getCustomTypeName(): ?string | setCustomTypeName(?string customTypeName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "contact": "people/c123456789",
  "customTypeName": "Wedding Anniversary",
  "type": "anniversary",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

