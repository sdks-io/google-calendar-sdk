
# Conference Create Request Status

Status of the conference create request.

*This model accepts additional fields of type array.*

## Structure

`ConferenceCreateRequestStatus`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `statusCode` | [`?string(ConferenceRequestStatusCode)`](../../doc/models/conference-request-status-code.md) | Optional | Status of the conference create request. | getStatusCode(): ?string | setStatusCode(?string statusCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "statusCode": "pending",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

