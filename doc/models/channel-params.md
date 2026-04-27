
# Channel Params

Additional parameters controlling delivery channel behavior.

*This model accepts additional fields of type array.*

## Structure

`ChannelParams`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ttl` | `?string` | Optional | The time-to-live in seconds for the notification channel. Default is 604800 (1 week). | getTtl(): ?string | setTtl(?string ttl): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "ttl": "604800",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

