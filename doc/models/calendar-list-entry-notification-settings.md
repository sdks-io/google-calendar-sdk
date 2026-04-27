
# Calendar List Entry Notification Settings

The notifications the authenticated user receives for this calendar.

*This model accepts additional fields of type array.*

## Structure

`CalendarListEntryNotificationSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `notifications` | [`?(CalendarNotification[])`](../../doc/models/calendar-notification.md) | Optional | List of notification settings for this calendar. | getNotifications(): ?array | setNotifications(?array notifications): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "notifications": [
    {
      "type": "eventCancellation",
      "method": "email",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "type": "eventCancellation",
      "method": "email",
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

