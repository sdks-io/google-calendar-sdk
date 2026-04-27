
# Calendar List Response

A paginated list of the user's calendar list entries.

*This model accepts additional fields of type array.*

## Structure

`CalendarListResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kind` | `?string` | Optional | Type of the collection.<br><br>**Default**: `'calendar#calendarList'` | getKind(): ?string | setKind(?string kind): void |
| `etag` | `?string` | Optional | ETag of the collection. | getEtag(): ?string | setEtag(?string etag): void |
| `nextPageToken` | `?string` | Optional | Token used to access the next page of this result. Omitted if no further results are available. | getNextPageToken(): ?string | setNextPageToken(?string nextPageToken): void |
| `nextSyncToken` | `?string` | Optional | Token used for incremental synchronization at a later point. Only provided on the last page of results. | getNextSyncToken(): ?string | setNextSyncToken(?string nextSyncToken): void |
| `items` | [`?(CalendarListEntry[])`](../../doc/models/calendar-list-entry.md) | Optional | Calendars on the user's calendar list. | getItems(): ?array | setItems(?array items): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "kind": "calendar#calendarList",
  "etag": "\"etag_value\"",
  "nextPageToken": "CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA",
  "nextSyncToken": "CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA",
  "items": [
    {
      "kind": "kind6",
      "etag": "etag4",
      "id": "id8",
      "summary": "summary0",
      "description": "description2",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "kind": "kind6",
      "etag": "etag4",
      "id": "id8",
      "summary": "summary0",
      "description": "description2",
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

