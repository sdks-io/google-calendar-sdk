
# Conference Create Request

A request to generate a new conference and attach it to the event.

*This model accepts additional fields of type array.*

## Structure

`ConferenceCreateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `requestId` | `?string` | Optional | Unique client-generated ID for this request. Clients should regenerate this ID for every new request. | getRequestId(): ?string | setRequestId(?string requestId): void |
| `conferenceSolutionKey` | [`?ConferenceSolutionKey`](../../doc/models/conference-solution-key.md) | Optional | Identifies a conference solution type. | getConferenceSolutionKey(): ?ConferenceSolutionKey | setConferenceSolutionKey(?ConferenceSolutionKey conferenceSolutionKey): void |
| `status` | [`?ConferenceCreateRequestStatus`](../../doc/models/conference-create-request-status.md) | Optional | Status of the conference create request. | getStatus(): ?ConferenceCreateRequestStatus | setStatus(?ConferenceCreateRequestStatus status): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "requestId": "req-7br2q3k68p36c",
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
}
```

