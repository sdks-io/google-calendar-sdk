
# Watch Request

Request body to set up a push notification channel.

*This model accepts additional fields of type array.*

## Structure

`WatchRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | A UUID or similar unique string that identifies this channel. | getId(): string | setId(string id): void |
| `token` | `?string` | Optional | An arbitrary string delivered to the target address with each notification. Optional. | getToken(): ?string | setToken(?string token): void |
| `type` | [`string(ChannelType)`](../../doc/models/channel-type.md) | Required | The type of delivery mechanism used for the notification channel. | getType(): string | setType(string type): void |
| `address` | `string` | Required | The address where notifications are delivered for this channel. Must be HTTPS. | getAddress(): string | setAddress(string address): void |
| `params` | [`?ChannelParams`](../../doc/models/channel-params.md) | Optional | Additional parameters controlling delivery channel behavior. | getParams(): ?ChannelParams | setParams(?ChannelParams params): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "token": "CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA",
  "type": "web_hook",
  "address": "https://example.com",
  "params": {
    "ttl": "ttl6",
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

