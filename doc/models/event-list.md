
# Event List

A paginated list of events on a calendar.

*This model accepts additional fields of type array.*

## Structure

`EventList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kind` | `?string` | Optional | Type of the collection.<br><br>**Default**: `'calendar#events'` | getKind(): ?string | setKind(?string kind): void |
| `etag` | `?string` | Optional | ETag of the collection. | getEtag(): ?string | setEtag(?string etag): void |
| `summary` | `?string` | Optional | Title of the calendar. | getSummary(): ?string | setSummary(?string summary): void |
| `description` | `?string` | Optional | Description of the calendar. | getDescription(): ?string | setDescription(?string description): void |
| `updated` | `?DateTime` | Optional | Last modification time of the calendar (RFC3339). | getUpdated(): ?\DateTime | setUpdated(?\DateTime updated): void |
| `timeZone` | `?string` | Optional | The time zone of the calendar. | getTimeZone(): ?string | setTimeZone(?string timeZone): void |
| `accessRole` | [`?string(CalendarAccessRole)`](../../doc/models/calendar-access-role.md) | Optional | The user's access role for a calendar. | getAccessRole(): ?string | setAccessRole(?string accessRole): void |
| `defaultReminders` | [`?(Reminder[])`](../../doc/models/reminder.md) | Optional | Default reminders on the calendar for the authenticated user. | getDefaultReminders(): ?array | setDefaultReminders(?array defaultReminders): void |
| `nextPageToken` | `?string` | Optional | Token used to access the next page of this result. Omitted if no further results are available. | getNextPageToken(): ?string | setNextPageToken(?string nextPageToken): void |
| `nextSyncToken` | `?string` | Optional | Token used for incremental synchronization at a later point. Only provided on the last page of results. | getNextSyncToken(): ?string | setNextSyncToken(?string nextSyncToken): void |
| `items` | [`?(Event[])`](../../doc/models/event.md) | Optional | List of events on the calendar. | getItems(): ?array | setItems(?array items): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "kind": "calendar#events",
  "etag": "\"etag_value\"",
  "summary": "Work Calendar",
  "description": "Shared calendar for the product team.",
  "updated": "01/15/2024 09:00:00",
  "timeZone": "America/New_York",
  "nextPageToken": "CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA",
  "nextSyncToken": "CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

