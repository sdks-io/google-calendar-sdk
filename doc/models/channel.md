
# Channel

A notification channel used to watch for resource changes.

*This model accepts additional fields of type array.*

## Structure

`Channel`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kind` | `?string` | Optional | Identifies this as a notification channel used to watch for changes to a resource.<br><br>**Default**: `'api#channel'` | getKind(): ?string | setKind(?string kind): void |
| `id` | `?string` | Optional | A UUID or similar unique string that identifies this channel. | getId(): ?string | setId(?string id): void |
| `resourceId` | `?string` | Optional | An opaque value that identifies the resource being watched on this channel. | getResourceId(): ?string | setResourceId(?string resourceId): void |
| `resourceUri` | `?string` | Optional | A version-specific identifier for the watched resource. | getResourceUri(): ?string | setResourceUri(?string resourceUri): void |
| `token` | `?string` | Optional | An arbitrary string delivered to the target address with each notification. | getToken(): ?string | setToken(?string token): void |
| `expiration` | `?int` | Optional | Date and time of notification channel expiration, expressed as a Unix timestamp, in milliseconds. | getExpiration(): ?int | setExpiration(?int expiration): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "kind": "api#channel",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "resourceId": "o3hgv1538sdjfh",
  "resourceUri": "https://example.com",
  "token": "CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA",
  "expiration": 1735689600000,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

