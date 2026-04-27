
# Error Response Error Errors Items

ErrorResponseErrorErrorsItems object.

*This model accepts additional fields of type array.*

## Structure

`ErrorResponseErrorErrorsItems`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `domain` | `?string` | Optional | The error domain. | getDomain(): ?string | setDomain(?string domain): void |
| `reason` | `?string` | Optional | The error reason code. | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | A human-readable error message. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "domain": "calendar",
  "reason": "notFound",
  "message": "Resource not found.",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

