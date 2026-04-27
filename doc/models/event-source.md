
# Event Source

Source from which the event was created — for example, a web page or an email message.

*This model accepts additional fields of type array.*

## Structure

`EventSource`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `url` | `?string` | Optional | URL of the source pointing to a resource. | getUrl(): ?string | setUrl(?string url): void |
| `title` | `?string` | Optional | Title of the source (e.g. a web page or email subject). | getTitle(): ?string | setTitle(?string title): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "url": "https://example.com",
  "title": "Project Planning Sheet",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

