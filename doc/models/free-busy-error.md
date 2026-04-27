
# Free Busy Error

An error associated with a free/busy calendar or group query.

*This model accepts additional fields of type array.*

## Structure

`FreeBusyError`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `domain` | `?string` | Optional | The error domain. | getDomain(): ?string | setDomain(?string domain): void |
| `reason` | `?string` | Optional | The error reason code. | getReason(): ?string | setReason(?string reason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "domain": "calendar",
  "reason": "notFound",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

