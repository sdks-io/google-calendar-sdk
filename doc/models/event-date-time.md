
# Event Date Time

A timestamp marking the start or end of an event. For all-day events, use date; for timed events, use dateTime.

*This model accepts additional fields of type array.*

## Structure

`EventDateTime`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `date` | `?DateTime` | Optional | The date, in the format "yyyy-mm-dd", if this is an all-day event. | getDate(): ?\DateTime | setDate(?\DateTime date): void |
| `dateTime` | `?DateTime` | Optional | The time, as a combined date-time value (RFC3339). A time zone offset is required unless a time zone is explicitly specified in timeZone. | getDateTime(): ?\DateTime | setDateTime(?\DateTime dateTime): void |
| `timeZone` | `?string` | Optional | The time zone in which the time is specified. Formatted as an IANA Time Zone Database name, e.g. "America/New_York". | getTimeZone(): ?string | setTimeZone(?string timeZone): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "date": "2024-01-15",
  "dateTime": "01/15/2024 09:00:00",
  "timeZone": "America/New_York",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

