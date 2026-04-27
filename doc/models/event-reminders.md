
# Event Reminders

Information about the event's reminders.

*This model accepts additional fields of type array.*

## Structure

`EventReminders`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `useDefault` | `?bool` | Optional | Whether the default reminders of the calendar apply to the event. | getUseDefault(): ?bool | setUseDefault(?bool useDefault): void |
| `overrides` | [`?(Reminder[])`](../../doc/models/reminder.md) | Optional | Overrides to apply instead of default reminders. Maximum 5 overrides.<br><br>**Constraints**: *Maximum Items*: `5` | getOverrides(): ?array | setOverrides(?array overrides): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "useDefault": false,
  "overrides": [
    {
      "method": "email",
      "minutes": 238,
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

