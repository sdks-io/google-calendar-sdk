
# Event

A Google Calendar event resource.

*This model accepts additional fields of type array.*

## Structure

`Event`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kind` | `?string` | Optional | Type of the resource.<br><br>**Default**: `'calendar#event'` | getKind(): ?string | setKind(?string kind): void |
| `etag` | `?string` | Optional | ETag of the resource. | getEtag(): ?string | setEtag(?string etag): void |
| `id` | `?string` | Optional | Opaque identifier of the event. When creating new single or recurring events, you can specify their IDs. Event IDs must be between 5 and 1024 characters long and consist of lower-case base32hex characters (a-v, 0-9).<br><br>**Constraints**: *Pattern*: `^[a-v0-9]{5,1024}$` | getId(): ?string | setId(?string id): void |
| `status` | [`?string(EventStatus)`](../../doc/models/event-status.md) | Optional | Status of the event. | getStatus(): ?string | setStatus(?string status): void |
| `htmlLink` | `?string` | Optional | Absolute link to this event in the Google Calendar Web UI. | getHtmlLink(): ?string | setHtmlLink(?string htmlLink): void |
| `created` | `?DateTime` | Optional | Creation time of the event (RFC3339). | getCreated(): ?\DateTime | setCreated(?\DateTime created): void |
| `updated` | `?DateTime` | Optional | Last modification time of the event (RFC3339). | getUpdated(): ?\DateTime | setUpdated(?\DateTime updated): void |
| `summary` | `?string` | Optional | Title of the event. | getSummary(): ?string | setSummary(?string summary): void |
| `description` | `?string` | Optional | Description of the event. Can contain HTML. | getDescription(): ?string | setDescription(?string description): void |
| `location` | `?string` | Optional | Geographic location of the event as free-form text. | getLocation(): ?string | setLocation(?string location): void |
| `colorId` | `?string` | Optional | The color of the event. This is an ID referring to an entry in the event section of the colors definition. | getColorId(): ?string | setColorId(?string colorId): void |
| `creator` | [`?Person`](../../doc/models/person.md) | Optional | Identifies a person associated with the event, such as the creator or organizer. | getCreator(): ?Person | setCreator(?Person creator): void |
| `organizer` | [`?Person`](../../doc/models/person.md) | Optional | Identifies a person associated with the event, such as the creator or organizer. | getOrganizer(): ?Person | setOrganizer(?Person organizer): void |
| `start` | [`EventDateTime`](../../doc/models/event-date-time.md) | Required | A timestamp marking the start or end of an event. For all-day events, use date; for timed events, use dateTime. | getStart(): EventDateTime | setStart(EventDateTime start): void |
| `end` | [`EventDateTime`](../../doc/models/event-date-time.md) | Required | A timestamp marking the start or end of an event. For all-day events, use date; for timed events, use dateTime. | getEnd(): EventDateTime | setEnd(EventDateTime end): void |
| `endTimeUnspecified` | `?bool` | Optional | Whether the end time is actually unspecified.<br><br>**Default**: `false` | getEndTimeUnspecified(): ?bool | setEndTimeUnspecified(?bool endTimeUnspecified): void |
| `recurrence` | `?(string[])` | Optional | List of RRULE, EXRULE, RDATE, and EXDATE lines for a recurring event, as specified in RFC 5545. This field is omitted for single events or instances of recurring events. | getRecurrence(): ?array | setRecurrence(?array recurrence): void |
| `recurringEventId` | `?string` | Optional | For an instance of a recurring event, this is the ID of the recurring event to which this instance belongs. | getRecurringEventId(): ?string | setRecurringEventId(?string recurringEventId): void |
| `originalStartTime` | [`?EventDateTime`](../../doc/models/event-date-time.md) | Optional | A timestamp marking the start or end of an event. For all-day events, use date; for timed events, use dateTime. | getOriginalStartTime(): ?EventDateTime | setOriginalStartTime(?EventDateTime originalStartTime): void |
| `transparency` | [`?string(EventTransparency)`](../../doc/models/event-transparency.md) | Optional | Whether the event blocks time on the calendar. "opaque" means the event does block time; "transparent" means it does not.<br><br>**Default**: `EventTransparency::OPAQUE` | getTransparency(): ?string | setTransparency(?string transparency): void |
| `visibility` | [`?string(EventVisibility)`](../../doc/models/event-visibility.md) | Optional | Visibility of the event.<br><br>**Default**: `EventVisibility::DEFAULT_` | getVisibility(): ?string | setVisibility(?string visibility): void |
| `iCalUid` | `?string` | Optional | Event unique identifier as defined in RFC 5545. | getICalUid(): ?string | setICalUid(?string iCalUid): void |
| `sequence` | `?int` | Optional | Sequence number as per iCalendar. | getSequence(): ?int | setSequence(?int sequence): void |
| `attendees` | [`?(Attendee[])`](../../doc/models/attendee.md) | Optional | The attendees of the event. | getAttendees(): ?array | setAttendees(?array attendees): void |
| `attendeesOmitted` | `?bool` | Optional | Whether attendees may have been omitted from the event's representation.<br><br>**Default**: `false` | getAttendeesOmitted(): ?bool | setAttendeesOmitted(?bool attendeesOmitted): void |
| `hangoutLink` | `?string` | Optional | An absolute link to the Google Hangout associated with this event (deprecated in favor of conferenceData). | getHangoutLink(): ?string | setHangoutLink(?string hangoutLink): void |
| `conferenceData` | [`?ConferenceData`](../../doc/models/conference-data.md) | Optional | Information about a conference (e.g. Google Meet). | getConferenceData(): ?ConferenceData | setConferenceData(?ConferenceData conferenceData): void |
| `guestsCanInviteOthers` | `?bool` | Optional | Whether attendees other than the organizer can invite others.<br><br>**Default**: `true` | getGuestsCanInviteOthers(): ?bool | setGuestsCanInviteOthers(?bool guestsCanInviteOthers): void |
| `guestsCanModify` | `?bool` | Optional | Whether attendees other than the organizer can modify the event.<br><br>**Default**: `false` | getGuestsCanModify(): ?bool | setGuestsCanModify(?bool guestsCanModify): void |
| `guestsCanSeeOtherGuests` | `?bool` | Optional | Whether attendees other than the organizer can see who the event's attendees are.<br><br>**Default**: `true` | getGuestsCanSeeOtherGuests(): ?bool | setGuestsCanSeeOtherGuests(?bool guestsCanSeeOtherGuests): void |
| `privateCopy` | `?bool` | Optional | If set to true, event propagation is disabled.<br><br>**Default**: `false` | getPrivateCopy(): ?bool | setPrivateCopy(?bool privateCopy): void |
| `locked` | `?bool` | Optional | Whether this is a locked event copy where no changes can be made.<br><br>**Default**: `false` | getLocked(): ?bool | setLocked(?bool locked): void |
| `reminders` | [`?EventReminders`](../../doc/models/event-reminders.md) | Optional | Information about the event's reminders. | getReminders(): ?EventReminders | setReminders(?EventReminders reminders): void |
| `source` | [`?EventSource`](../../doc/models/event-source.md) | Optional | Source from which the event was created — for example, a web page or an email message. | getSource(): ?EventSource | setSource(?EventSource source): void |
| `eventType` | [`?string(EventType)`](../../doc/models/event-type.md) | Optional | The specific type of event. | getEventType(): ?string | setEventType(?string eventType): void |
| `extendedProperties` | [`?ExtendedProperties`](../../doc/models/extended-properties.md) | Optional | Extended properties of the event. | getExtendedProperties(): ?ExtendedProperties | setExtendedProperties(?ExtendedProperties extendedProperties): void |
| `attachments` | [`?(Attachment[])`](../../doc/models/attachment.md) | Optional | File attachments for the event. Maximum 25 attachments per event.<br><br>**Constraints**: *Maximum Items*: `25` | getAttachments(): ?array | setAttachments(?array attachments): void |
| `birthdayProperties` | [`?BirthdayProperties`](../../doc/models/birthday-properties.md) | Optional | Birthday or special event data. Used if eventType is birthday. | getBirthdayProperties(): ?BirthdayProperties | setBirthdayProperties(?BirthdayProperties birthdayProperties): void |
| `outOfOfficeProperties` | [`?OutOfOfficeProperties`](../../doc/models/out-of-office-properties.md) | Optional | Out-of-office event data. Used if eventType is outOfOffice. | getOutOfOfficeProperties(): ?OutOfOfficeProperties | setOutOfOfficeProperties(?OutOfOfficeProperties outOfOfficeProperties): void |
| `focusTimeProperties` | [`?FocusTimeProperties`](../../doc/models/focus-time-properties.md) | Optional | Focus time event data. Used if eventType is focusTime. | getFocusTimeProperties(): ?FocusTimeProperties | setFocusTimeProperties(?FocusTimeProperties focusTimeProperties): void |
| `workingLocationProperties` | [`?WorkingLocationProperties`](../../doc/models/working-location-properties.md) | Optional | Working location event data. Used if eventType is workingLocation. | getWorkingLocationProperties(): ?WorkingLocationProperties | setWorkingLocationProperties(?WorkingLocationProperties workingLocationProperties): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "kind": "calendar#event",
  "etag": "\"etag_value\"",
  "id": "abc123",
  "htmlLink": "https://example.com",
  "created": "01/15/2024 09:00:00",
  "updated": "01/15/2024 09:00:00",
  "summary": "Team Weekly Standup",
  "description": "Weekly sync with the product team.",
  "location": "123 Main St, City",
  "colorId": "1",
  "start": {
    "date": "2024-01-15",
    "dateTime": "01/15/2024 09:00:00",
    "timeZone": "America/New_York",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "end": {
    "date": "2024-01-15",
    "dateTime": "01/15/2024 09:00:00",
    "timeZone": "America/New_York",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "endTimeUnspecified": false,
  "recurringEventId": "abc123",
  "transparency": "opaque",
  "visibility": "default",
  "iCalUID": "unique-event-id@google.com",
  "sequence": 0,
  "attendeesOmitted": false,
  "hangoutLink": "https://example.com",
  "guestsCanInviteOthers": true,
  "guestsCanModify": false,
  "guestsCanSeeOtherGuests": true,
  "privateCopy": false,
  "locked": false,
  "status": "cancelled",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

