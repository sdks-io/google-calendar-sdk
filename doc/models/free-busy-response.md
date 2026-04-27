
# Free Busy Response

Response with free/busy information.

*This model accepts additional fields of type array.*

## Structure

`FreeBusyResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kind` | `?string` | Optional | Type of the resource.<br><br>**Default**: `'calendar#freeBusy'` | getKind(): ?string | setKind(?string kind): void |
| `timeMin` | `?DateTime` | Optional | The start of the time range queried. | getTimeMin(): ?\DateTime | setTimeMin(?\DateTime timeMin): void |
| `timeMax` | `?DateTime` | Optional | The end of the time range queried. | getTimeMax(): ?\DateTime | setTimeMax(?\DateTime timeMax): void |
| `calendars` | [`?array<string,FreeBusyCalendar>`](../../doc/models/free-busy-calendar.md) | Optional | Free/busy information for each requested calendar. | getCalendars(): ?array | setCalendars(?array calendars): void |
| `groups` | [`?array<string,FreeBusyGroup>`](../../doc/models/free-busy-group.md) | Optional | Expansion of groups. | getGroups(): ?array | setGroups(?array groups): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "kind": "calendar#freeBusy",
  "timeMin": "01/15/2024 09:00:00",
  "timeMax": "01/15/2024 09:00:00",
  "calendars": {
    "key0": {
      "busy": [
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
        }
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "key1": {
      "busy": [
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
        }
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "key2": {
      "busy": [
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
        }
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  },
  "groups": {
    "key0": {
      "calendars": [
        "calendars5"
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
        }
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

