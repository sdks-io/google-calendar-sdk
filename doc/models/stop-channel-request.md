
# Stop Channel Request

Request body to stop a push notification channel. Requires the channel ID and resourceId returned from a previous watchEvents call.

*This model accepts additional fields of type array.*

## Structure

`StopChannelRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | The UUID or unique string that identifies the channel, as provided when the channel was created. | getId(): string | setId(string id): void |
| `resourceId` | `string` | Required | An opaque ID that identifies the resource being watched on this channel. Returned in the watchEvents response. | getResourceId(): string | setResourceId(string resourceId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "resourceId": "o3hgv1538sdjfh",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

