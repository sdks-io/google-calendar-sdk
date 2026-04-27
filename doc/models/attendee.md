
# Attendee

An attendee of an event.

*This model accepts additional fields of type array.*

## Structure

`Attendee`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The attendee's Profile ID. | getId(): ?string | setId(?string id): void |
| `email` | `?string` | Optional | The attendee's email address. Required when adding an attendee. | getEmail(): ?string | setEmail(?string email): void |
| `displayName` | `?string` | Optional | The attendee's name. | getDisplayName(): ?string | setDisplayName(?string displayName): void |
| `organizer` | `?bool` | Optional | Whether the attendee is the organizer of the event. | getOrganizer(): ?bool | setOrganizer(?bool organizer): void |
| `self` | `?bool` | Optional | Whether this entry represents the calendar on which this copy of the event appears. | getSelf(): ?bool | setSelf(?bool self): void |
| `resource` | `?bool` | Optional | Whether the attendee is a resource (e.g. a room). | getResource(): ?bool | setResource(?bool resource): void |
| `optional` | `?bool` | Optional | Whether this is an optional attendee.<br><br>**Default**: `false` | getOptional(): ?bool | setOptional(?bool optional): void |
| `responseStatus` | [`?string(ResponseStatus)`](../../doc/models/response-status.md) | Optional | The attendee's response status. | getResponseStatus(): ?string | setResponseStatus(?string responseStatus): void |
| `comment` | `?string` | Optional | The attendee's response comment. | getComment(): ?string | setComment(?string comment): void |
| `additionalGuests` | `?int` | Optional | Number of additional guests the attendee is bringing.<br><br>**Default**: `0`<br><br>**Constraints**: `>= 0` | getAdditionalGuests(): ?int | setAdditionalGuests(?int additionalGuests): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "id": "abc123",
  "email": "user@example.com",
  "displayName": "Google Meet",
  "organizer": false,
  "self": false,
  "resource": false,
  "optional": false,
  "comment": "Looking forward to it!",
  "additionalGuests": 0,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

