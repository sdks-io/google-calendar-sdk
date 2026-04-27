
# Free Busy Request

Request body for querying free/busy information.

*This model accepts additional fields of type array.*

## Structure

`FreeBusyRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `timeMin` | `DateTime` | Required | The start of the interval for the query (RFC3339). | getTimeMin(): \DateTime | setTimeMin(\DateTime timeMin): void |
| `timeMax` | `DateTime` | Required | The end of the interval for the query (RFC3339). | getTimeMax(): \DateTime | setTimeMax(\DateTime timeMax): void |
| `timeZone` | `?string` | Optional | Time zone used in the response. Optional. Defaults to UTC. | getTimeZone(): ?string | setTimeZone(?string timeZone): void |
| `groupExpansionMax` | `?int` | Optional | Maximal number of calendar identifiers to be provided for a single group. Maximum value is 100.<br><br>**Constraints**: `>= 1`, `<= 100` | getGroupExpansionMax(): ?int | setGroupExpansionMax(?int groupExpansionMax): void |
| `calendarExpansionMax` | `?int` | Optional | Maximal number of calendars whose free/busy information is to be returned. Maximum value is 50.<br><br>**Constraints**: `>= 1`, `<= 50` | getCalendarExpansionMax(): ?int | setCalendarExpansionMax(?int calendarExpansionMax): void |
| `items` | [`FreeBusyRequestItem[]`](../../doc/models/free-busy-request-item.md) | Required | List of calendars and/or groups to query. | getItems(): array | setItems(array items): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "timeMin": "01/15/2024 09:00:00",
  "timeMax": "01/15/2024 09:00:00",
  "timeZone": "America/New_York",
  "groupExpansionMax": 50,
  "calendarExpansionMax": 25,
  "items": [
    {
      "id": "primary",
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

