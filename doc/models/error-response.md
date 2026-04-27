
# Error Response

Standard Google API error response wrapper.

*This model accepts additional fields of type array.*

## Structure

`ErrorResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `error` | [`?ErrorResponseError`](../../doc/models/error-response-error.md) | Optional | Error details. | getError(): ?ErrorResponseError | setError(?ErrorResponseError error): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "error": {
    "code": 24,
    "message": "message4",
    "errors": [
      {
        "domain": "domain6",
        "reason": "reason4",
        "message": "message0",
        "exampleAdditionalProperty": {
          "key1": "val1",
          "key2": "val2"
        }
      },
      {
        "domain": "domain6",
        "reason": "reason4",
        "message": "message0",
        "exampleAdditionalProperty": {
          "key1": "val1",
          "key2": "val2"
        }
      },
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
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

