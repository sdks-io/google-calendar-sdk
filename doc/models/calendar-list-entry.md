
# Calendar List Entry

An entry on the user's calendar list.

*This model accepts additional fields of type array.*

## Structure

`CalendarListEntry`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kind` | `?string` | Optional | Type of the resource.<br><br>**Default**: `'calendar#calendarListEntry'` | getKind(): ?string | setKind(?string kind): void |
| `etag` | `?string` | Optional | ETag of the resource. | getEtag(): ?string | setEtag(?string etag): void |
| `id` | `?string` | Optional | Identifier of the calendar. Use this value as the calendarId path parameter in event operations. | getId(): ?string | setId(?string id): void |
| `summary` | `?string` | Optional | Title of the calendar. | getSummary(): ?string | setSummary(?string summary): void |
| `description` | `?string` | Optional | Description of the calendar. | getDescription(): ?string | setDescription(?string description): void |
| `location` | `?string` | Optional | Geographic location of the calendar as free-form text. | getLocation(): ?string | setLocation(?string location): void |
| `timeZone` | `?string` | Optional | The time zone of the calendar. | getTimeZone(): ?string | setTimeZone(?string timeZone): void |
| `summaryOverride` | `?string` | Optional | The summary that the authenticated user has set for this calendar. | getSummaryOverride(): ?string | setSummaryOverride(?string summaryOverride): void |
| `colorId` | `?string` | Optional | The color of the calendar. References an entry in the calendar section of the colors definition. | getColorId(): ?string | setColorId(?string colorId): void |
| `backgroundColor` | `?string` | Optional | The main color of the calendar in hexadecimal format (e.g. "#0088aa"). | getBackgroundColor(): ?string | setBackgroundColor(?string backgroundColor): void |
| `foregroundColor` | `?string` | Optional | The foreground color of the calendar in hexadecimal format (e.g. "#ffffff"). | getForegroundColor(): ?string | setForegroundColor(?string foregroundColor): void |
| `hidden` | `?bool` | Optional | Whether the calendar has been hidden from the list.<br><br>**Default**: `false` | getHidden(): ?bool | setHidden(?bool hidden): void |
| `selected` | `?bool` | Optional | Whether the calendar content shows up in the calendar UI.<br><br>**Default**: `false` | getSelected(): ?bool | setSelected(?bool selected): void |
| `accessRole` | [`?string(CalendarAccessRole)`](../../doc/models/calendar-access-role.md) | Optional | The user's access role for a calendar. | getAccessRole(): ?string | setAccessRole(?string accessRole): void |
| `defaultReminders` | [`?(Reminder[])`](../../doc/models/reminder.md) | Optional | The default reminders that the authenticated user has for this calendar. | getDefaultReminders(): ?array | setDefaultReminders(?array defaultReminders): void |
| `notificationSettings` | [`?CalendarListEntryNotificationSettings`](../../doc/models/calendar-list-entry-notification-settings.md) | Optional | The notifications the authenticated user receives for this calendar. | getNotificationSettings(): ?CalendarListEntryNotificationSettings | setNotificationSettings(?CalendarListEntryNotificationSettings notificationSettings): void |
| `primary` | `?bool` | Optional | Whether the calendar is the primary calendar of the authenticated user. | getPrimary(): ?bool | setPrimary(?bool primary): void |
| `deleted` | `?bool` | Optional | Whether the calendar list entry has been removed from the list.<br><br>**Default**: `false` | getDeleted(): ?bool | setDeleted(?bool deleted): void |
| `conferenceProperties` | [`?CalendarListEntryConferenceProperties`](../../doc/models/calendar-list-entry-conference-properties.md) | Optional | Conference properties for this calendar. | getConferenceProperties(): ?CalendarListEntryConferenceProperties | setConferenceProperties(?CalendarListEntryConferenceProperties conferenceProperties): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "kind": "calendar#calendarListEntry",
  "etag": "\"etag_value\"",
  "id": "user@example.com",
  "summary": "Work Calendar",
  "description": "Shared calendar for the product team.",
  "location": "123 Main St, City",
  "timeZone": "America/New_York",
  "summaryOverride": "My Work Calendar",
  "colorId": "1",
  "backgroundColor": "#0088aa",
  "foregroundColor": "#ffffff",
  "hidden": false,
  "selected": false,
  "primary": false,
  "deleted": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

