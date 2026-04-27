
# Error Response Error

Error details.

*This model accepts additional fields of type array.*

## Structure

`ErrorResponseError`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?int` | Optional | HTTP status code. | getCode(): ?int | setCode(?int code): void |
| `message` | `?string` | Optional | A human-readable description of the error. | getMessage(): ?string | setMessage(?string message): void |
| `errors` | [`?(ErrorResponseErrorErrorsItems[])`](../../doc/models/error-response-error-errors-items.md) | Optional | List of individual errors. | getErrors(): ?array | setErrors(?array errors): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "code": 404,
  "message": "Resource not found.",
  "errors": [
    {
      "domain": "domain6",
      "reason": "reason4",
      "message": "message0",
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
```

