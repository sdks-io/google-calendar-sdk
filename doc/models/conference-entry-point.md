
# Conference Entry Point

Information about an individual conference entry point.

*This model accepts additional fields of type array.*

## Structure

`ConferenceEntryPoint`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entryPointType` | [`?string(EntryPointType)`](../../doc/models/entry-point-type.md) | Optional | The type of conference entry point. | getEntryPointType(): ?string | setEntryPointType(?string entryPointType): void |
| `uri` | `?string` | Optional | The URI of the entry point. Maximum length is 1300 characters.<br><br>**Constraints**: *Maximum Length*: `1300` | getUri(): ?string | setUri(?string uri): void |
| `label` | `?string` | Optional | The label for the URI. | getLabel(): ?string | setLabel(?string label): void |
| `pin` | `?string` | Optional | The PIN to access the conference. | getPin(): ?string | setPin(?string pin): void |
| `meetingCode` | `?string` | Optional | The meeting code to access the conference. | getMeetingCode(): ?string | setMeetingCode(?string meetingCode): void |
| `password` | `?string` | Optional | The password to access the conference. | getPassword(): ?string | setPassword(?string password): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "uri": "https://example.com",
  "label": "Join via Google Meet",
  "pin": "123456",
  "meetingCode": "abc-defg-hij",
  "password": "abc-defg-hij",
  "entryPointType": "video",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

