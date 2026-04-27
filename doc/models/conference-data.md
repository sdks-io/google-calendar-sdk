
# Conference Data

Information about a conference (e.g. Google Meet).

*This model accepts additional fields of type array.*

## Structure

`ConferenceData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createRequest` | [`?ConferenceCreateRequest`](../../doc/models/conference-create-request.md) | Optional | A request to generate a new conference and attach it to the event. | getCreateRequest(): ?ConferenceCreateRequest | setCreateRequest(?ConferenceCreateRequest createRequest): void |
| `entryPoints` | [`?(ConferenceEntryPoint[])`](../../doc/models/conference-entry-point.md) | Optional | Information about individual conference entry points. | getEntryPoints(): ?array | setEntryPoints(?array entryPoints): void |
| `conferenceSolution` | [`?ConferenceSolution`](../../doc/models/conference-solution.md) | Optional | Conference solution information, such as Google Meet. | getConferenceSolution(): ?ConferenceSolution | setConferenceSolution(?ConferenceSolution conferenceSolution): void |
| `conferenceId` | `?string` | Optional | The ID of the conference. | getConferenceId(): ?string | setConferenceId(?string conferenceId): void |
| `notes` | `?string` | Optional | Additional notes to display to the user. May contain HTML. | getNotes(): ?string | setNotes(?string notes): void |
| `signature` | `?string` | Optional | Server-generated signature of the conference data. | getSignature(): ?string | setSignature(?string signature): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "conferenceId": "abc123",
  "notes": "Join via Google Meet",
  "signature": "ADqupKAXQVTm0QAAAAG1WGkfpA==",
  "createRequest": {
    "requestId": "requestId2",
    "conferenceSolutionKey": {
      "type": "type6",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "status": {
      "statusCode": "success",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "entryPoints": [
    {
      "entryPointType": "sip",
      "uri": "uri2",
      "label": "label8",
      "pin": "pin6",
      "meetingCode": "meetingCode6",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "entryPointType": "sip",
      "uri": "uri2",
      "label": "label8",
      "pin": "pin6",
      "meetingCode": "meetingCode6",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "conferenceSolution": {
    "key": {
      "type": "type0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "name": "name4",
    "iconUri": "iconUri6",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

