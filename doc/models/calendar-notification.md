
# Calendar Notification

A notification setting for a calendar.

*This model accepts additional fields of type array.*

## Structure

`CalendarNotification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | [`?string(CalendarNotificationType)`](../../doc/models/calendar-notification-type.md) | Optional | The type of notification. | getType(): ?string | setType(?string type): void |
| `method` | [`?string(CalendarNotificationMethod)`](../../doc/models/calendar-notification-method.md) | Optional | The method used to deliver the notification. Currently only "email" is supported. | getMethod(): ?string | setMethod(?string method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "type": "agenda",
  "method": "email",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

