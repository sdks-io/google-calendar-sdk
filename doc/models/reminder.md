
# Reminder

A reminder for an event.

*This model accepts additional fields of type array.*

## Structure

`Reminder`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | [`string(ReminderMethod)`](../../doc/models/reminder-method.md) | Required | The method used by a reminder. | getMethod(): string | setMethod(string method): void |
| `minutes` | `int` | Required | Number of minutes before the start of the event when the reminder should trigger. Valid values are between 0 and 40320 (4 weeks).<br><br>**Constraints**: `>= 0`, `<= 40320` | getMinutes(): int | setMinutes(int minutes): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "method": "email",
  "minutes": 30,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

