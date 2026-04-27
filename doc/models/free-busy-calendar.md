
# Free Busy Calendar

Free/busy data for a single calendar.

*This model accepts additional fields of type array.*

## Structure

`FreeBusyCalendar`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `busy` | [`?(TimePeriod[])`](../../doc/models/time-period.md) | Optional | List of time ranges during which this calendar is busy. | getBusy(): ?array | setBusy(?array busy): void |
| `errors` | [`?(FreeBusyError[])`](../../doc/models/free-busy-error.md) | Optional | Optional errors for this calendar. | getErrors(): ?array | setErrors(?array errors): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "busy": [
    {
      "start": "2016-03-13T12:52:32.123Z",
      "end": "2016-03-13T12:52:32.123Z",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "start": "2016-03-13T12:52:32.123Z",
      "end": "2016-03-13T12:52:32.123Z",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "errors": [
    {
      "domain": "domain6",
      "reason": "reason4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "domain": "domain6",
      "reason": "reason4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "domain": "domain6",
      "reason": "reason4",
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

