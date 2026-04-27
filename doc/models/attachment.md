
# Attachment

A file attachment for an event.

*This model accepts additional fields of type array.*

## Structure

`Attachment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fileUrl` | `?string` | Optional | URL link to the attachment. Required when adding an attachment. | getFileUrl(): ?string | setFileUrl(?string fileUrl): void |
| `title` | `?string` | Optional | Attachment title. | getTitle(): ?string | setTitle(?string title): void |
| `mimeType` | `?string` | Optional | Internet media type (MIME type) of the attachment. | getMimeType(): ?string | setMimeType(?string mimeType): void |
| `iconLink` | `?string` | Optional | URL link to the attachment's icon. | getIconLink(): ?string | setIconLink(?string iconLink): void |
| `fileId` | `?string` | Optional | ID of the attached file. Only populated for Google Drive files. | getFileId(): ?string | setFileId(?string fileId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "fileUrl": "https://example.com",
  "title": "Q4 Planning Document",
  "mimeType": "application/pdf",
  "iconLink": "https://example.com",
  "fileId": "abc123",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

