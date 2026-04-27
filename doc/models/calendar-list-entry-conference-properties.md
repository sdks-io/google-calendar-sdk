
# Calendar List Entry Conference Properties

Conference properties for this calendar.

*This model accepts additional fields of type array.*

## Structure

`CalendarListEntryConferenceProperties`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowedConferenceSolutionTypes` | [`?(string(ConferenceSolutionType)[])`](../../doc/models/conference-solution-type.md) | Optional | The types of conference solutions supported for this calendar. | getAllowedConferenceSolutionTypes(): ?array | setAllowedConferenceSolutionTypes(?array allowedConferenceSolutionTypes): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "allowedConferenceSolutionTypes": [
    "eventNamedHangout",
    "hangoutsMeet"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

