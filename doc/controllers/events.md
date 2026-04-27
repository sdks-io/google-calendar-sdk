# Events

Operations on calendar events.

```php
$eventsApi = $client->getEventsApi();
```

## Class Name

`EventsApi`

## Methods

* [List Events](../../doc/controllers/events.md#list-events)
* [Create Event](../../doc/controllers/events.md#create-event)
* [Patch Event](../../doc/controllers/events.md#patch-event)
* [Delete Event](../../doc/controllers/events.md#delete-event)
* [Watch Events](../../doc/controllers/events.md#watch-events)


# List Events

Returns events on the specified calendar. Results are paginated and ordered by start time (when singleEvents is true) or by last modification time (default).

```php
function listEvents(
    string $calendarId,
    ?array $eventTypes = null,
    ?string $iCalUid = null,
    ?int $maxAttendees = null,
    ?int $maxResults = 250,
    ?string $orderBy = null,
    ?string $pageToken = null,
    ?string $privateExtendedProperty = null,
    ?string $q = null,
    ?string $sharedExtendedProperty = null,
    ?bool $showDeleted = false,
    ?bool $showHiddenInvitations = false,
    ?bool $singleEvents = false,
    ?string $syncToken = null,
    ?\DateTime $timeMax = null,
    ?\DateTime $timeMin = null,
    ?string $timeZone = null,
    ?\DateTime $updatedMin = null
): ApiResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `calendarId` | `string` | Template, Required | Calendar identifier. To retrieve calendar IDs call the calendarList.list method. Use the keyword "primary" to access the primary calendar of the currently logged-in user. |
| `eventTypes` | [`?(string(EventType)[])`](../../doc/models/event-type.md) | Query, Optional | Filter by event type. May be repeated to include multiple types. |
| `iCalUid` | `?string` | Query, Optional | Specifies an iCalendar UID to search for. Only one event with the given UID will be returned. |
| `maxAttendees` | `?int` | Query, Optional | The maximum number of attendees to include in the response. If there are more attendees, only the participant is returned.<br><br>**Constraints**: `>= 1` |
| `maxResults` | `?int` | Query, Optional | Maximum number of events returned on one result page. The number of events in the resulting page may be less than this value. Default is 250, maximum allowed is 2500.<br><br>**Default**: `250`<br><br>**Constraints**: `>= 1`, `<= 2500` |
| `orderBy` | [`?string(EventOrderBy)`](../../doc/models/event-order-by.md) | Query, Optional | The order of the events returned in the result. When using orderBy with startTime, singleEvents must be true. |
| `pageToken` | `?string` | Query, Optional | Token specifying which result page to return. |
| `privateExtendedProperty` | `?string` | Query, Optional | Extended property constraint specified as propertyName=value. Matches only private properties. |
| `q` | `?string` | Query, Optional | Free text search terms to find events matching these terms in the summary, description, location, attendee's displayName, and attendee's email. |
| `sharedExtendedProperty` | `?string` | Query, Optional | Extended property constraint specified as propertyName=value. Matches only shared properties. |
| `showDeleted` | `?bool` | Query, Optional | Whether to include deleted events (with status equals "cancelled") in the result. Default is false.<br><br>**Default**: `false` |
| `showHiddenInvitations` | `?bool` | Query, Optional | Whether to include hidden invitations in the result. Default is false.<br><br>**Default**: `false` |
| `singleEvents` | `?bool` | Query, Optional | Whether to expand recurring events into instances and only return single one-off events and instances of recurring events. Default is false.<br><br>**Default**: `false` |
| `syncToken` | `?string` | Query, Optional | Token obtained from the nextSyncToken field returned on the last page of results from the previous list request. Makes the result contain only entries that have changed since then. Cannot be used together with iCalUID, orderBy, privateExtendedProperty, q, sharedExtendedProperty, timeMin, timeMax, or updatedMin. |
| `timeMax` | `?DateTime` | Query, Optional | Upper bound (exclusive) for an event's start time to filter by. Must be an RFC3339 timestamp with mandatory time zone offset. |
| `timeMin` | `?DateTime` | Query, Optional | Lower bound (exclusive) for an event's end time to filter by. Must be an RFC3339 timestamp with mandatory time zone offset. |
| `timeZone` | `?string` | Query, Optional | Time zone used in the response. Defaults to the time zone of the calendar. |
| `updatedMin` | `?DateTime` | Query, Optional | Lower bound for an event's last modification time (RFC3339 timestamp) to filter by. |

## Requires scope

### oauth2

`https://www.googleapis.com/auth/calendar`, `https://www.googleapis.com/auth/calendar.events`, `https://www.googleapis.com/auth/calendar.readonly`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`EventList`](../../doc/models/event-list.md).

## Example Usage

```php
$calendarId = 'primary';

$iCalUid = 'unique-event-id@google.com';

$maxAttendees = 1;

$maxResults = 1;

$orderBy = EventOrderBy::STARTTIME;

$pageToken = 'CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA';

$privateExtendedProperty = 'projectId=42';

$q = 'team lunch';

$sharedExtendedProperty = 'sharedKey=sharedValue';

$showDeleted = false;

$showHiddenInvitations = false;

$singleEvents = false;

$syncToken = 'CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA';

$timeMax = DateTimeHelper::fromRfc3339DateTime('01/15/2024 09:00:00');

$timeMin = DateTimeHelper::fromRfc3339DateTime('01/15/2024 09:00:00');

$timeZone = 'America/New_York';

$updatedMin = DateTimeHelper::fromRfc3339DateTime('01/15/2024 09:00:00');

$eventsApi = $client->getEventsApi();
$apiResponse = $eventsApi->listEvents(
    $calendarId,
    null,
    $iCalUid,
    $maxAttendees,
    $maxResults,
    $orderBy,
    $pageToken,
    $privateExtendedProperty,
    $q,
    $sharedExtendedProperty,
    $showDeleted,
    $showHiddenInvitations,
    $singleEvents,
    $syncToken,
    $timeMax,
    $timeMin,
    $timeZone,
    $updatedMin
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'EventList:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    if ($error instanceof ErrorResponseError1Exception) {
        echo 'ErrorResponseError1Exception:', $error;
    }
}
```

## Example Response *(as JSON)*

```json
{
  "kind": "calendar#events",
  "etag": "\"etag_value\"",
  "summary": "Work Calendar",
  "description": "Shared calendar for the product team.",
  "updated": "2024-01-15T09:00:00Z",
  "timeZone": "America/New_York",
  "nextPageToken": "CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA",
  "nextSyncToken": "CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request — invalid parameters or request body. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 401 | Authentication required or credentials are invalid. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 403 | Insufficient permissions for the requested resource. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 404 | The requested resource was not found. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |


# Create Event

Creates an event on the specified calendar.

```php
function createEvent(
    string $calendarId,
    Event $body,
    ?int $conferenceDataVersion = ConferenceDataVersion::ENUM_0,
    ?int $maxAttendees = null,
    ?string $sendUpdates = null,
    ?bool $supportsAttachments = false
): ApiResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `calendarId` | `string` | Template, Required | Calendar identifier. To retrieve calendar IDs call the calendarList.list method. Use the keyword "primary" to access the primary calendar of the currently logged-in user. |
| `body` | [`Event`](../../doc/models/event.md) | Body, Required | Request body for create an event. |
| `conferenceDataVersion` | [`?int(ConferenceDataVersion)`](../../doc/models/conference-data-version.md) | Query, Optional | Version number of conference data supported by the API client. Version 0 assumes no conference data support. Version 1 enables support for copying of ConferenceData as well as creating new conferences using createRequest.<br><br>**Default**: `ConferenceDataVersion::ENUM_0` |
| `maxAttendees` | `?int` | Query, Optional | The maximum number of attendees to include in the response.<br><br>**Constraints**: `>= 1` |
| `sendUpdates` | [`?string(SendUpdates)`](../../doc/models/send-updates.md) | Query, Optional | Whether to send notifications about the creation of the new event. |
| `supportsAttachments` | `?bool` | Query, Optional | Whether the API client performing the operation supports event attachments. Default is false.<br><br>**Default**: `false` |

## Requires scope

### oauth2

`https://www.googleapis.com/auth/calendar`, `https://www.googleapis.com/auth/calendar.events`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`Event`](../../doc/models/event.md).

## Example Usage

```php
$calendarId = 'primary';

$body = EventBuilder::init(
    EventDateTimeBuilder::init()
        ->dateTime(DateTimeHelper::fromRfc3339DateTime('2024-01-15T09:00:00Z'))
        ->timeZone('America/New_York')
        ->build(),
    EventDateTimeBuilder::init()
        ->dateTime(DateTimeHelper::fromRfc3339DateTime('2024-01-15T10:00:00Z'))
        ->timeZone('America/New_York')
        ->build()
)
    ->id('abc123')
    ->summary('Team Weekly Standup')
    ->description('Weekly sync with the product team.')
    ->location('123 Main St, City')
    ->colorId('1')
    ->sequence(0)
    ->attendeesOmitted(false)
    ->guestsCanInviteOthers(true)
    ->guestsCanModify(false)
    ->guestsCanSeeOtherGuests(true)
    ->build();

$conferenceDataVersion = ConferenceDataVersion::ENUM_0;

$maxAttendees = 1;

$sendUpdates = SendUpdates::NONE;

$supportsAttachments = false;

$eventsApi = $client->getEventsApi();
$apiResponse = $eventsApi->createEvent(
    $calendarId,
    $body,
    $conferenceDataVersion,
    $maxAttendees,
    $sendUpdates,
    $supportsAttachments
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'Event:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    if ($error instanceof ErrorResponseError1Exception) {
        echo 'ErrorResponseError1Exception:', $error;
    }
}
```

## Example Response *(as JSON)*

```json
{
  "kind": "calendar#event",
  "etag": "\"etag_value\"",
  "id": "abc123",
  "htmlLink": "https://example.com",
  "created": "2024-01-15T09:00:00Z",
  "updated": "2024-01-15T09:00:00Z",
  "summary": "Team Weekly Standup",
  "description": "Weekly sync with the product team.",
  "location": "123 Main St, City",
  "colorId": "1",
  "start": {
    "dateTime": "2024-01-15T09:00:00Z",
    "timeZone": "America/New_York"
  },
  "end": {
    "dateTime": "2024-01-15T10:00:00Z",
    "timeZone": "America/New_York"
  },
  "endTimeUnspecified": false,
  "recurringEventId": "abc123",
  "iCalUID": "unique-event-id@google.com",
  "sequence": 0,
  "attendeesOmitted": false,
  "hangoutLink": "https://example.com",
  "guestsCanInviteOthers": true,
  "guestsCanModify": false,
  "guestsCanSeeOtherGuests": true,
  "privateCopy": false,
  "locked": false
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request — invalid parameters or request body. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 401 | Authentication required or credentials are invalid. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 403 | Insufficient permissions for the requested resource. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 404 | The requested resource was not found. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 409 | Conflict — an event with the given ID already exists. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |


# Patch Event

Updates an event using patch semantics. Each patch request consumes three quota units. Only fields specified in the request body are modified; unspecified fields remain unchanged. Array fields, if specified, overwrite existing arrays entirely.

```php
function patchEvent(
    string $calendarId,
    string $eventId,
    Event $body,
    ?int $conferenceDataVersion = ConferenceDataVersion::ENUM_0,
    ?int $maxAttendees = null,
    ?string $sendUpdates = null,
    ?bool $supportsAttachments = false
): ApiResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `calendarId` | `string` | Template, Required | Calendar identifier. To retrieve calendar IDs call the calendarList.list method. Use the keyword "primary" to access the primary calendar of the currently logged-in user. |
| `eventId` | `string` | Template, Required | Event identifier. |
| `body` | [`Event`](../../doc/models/event.md) | Body, Required | Request body for update an event. |
| `conferenceDataVersion` | [`?int(ConferenceDataVersion)`](../../doc/models/conference-data-version.md) | Query, Optional | Version number of conference data supported by the API client.<br><br>**Default**: `ConferenceDataVersion::ENUM_0` |
| `maxAttendees` | `?int` | Query, Optional | The maximum number of attendees to include in the response.<br><br>**Constraints**: `>= 1` |
| `sendUpdates` | [`?string(SendUpdates)`](../../doc/models/send-updates.md) | Query, Optional | Whether to send notifications about the event update. |
| `supportsAttachments` | `?bool` | Query, Optional | Whether the API client performing the operation supports event attachments.<br><br>**Default**: `false` |

## Requires scope

### oauth2

`https://www.googleapis.com/auth/calendar`, `https://www.googleapis.com/auth/calendar.events`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`Event`](../../doc/models/event.md).

## Example Usage

```php
$calendarId = 'primary';

$eventId = 'abc123';

$body = EventBuilder::init(
    EventDateTimeBuilder::init()
        ->date(DateTimeHelper::fromSimpleDate('2024-01-15'))
        ->dateTime(DateTimeHelper::fromRfc3339DateTime('01/15/2024 09:00:00'))
        ->timeZone('America/New_York')
        ->build(),
    EventDateTimeBuilder::init()
        ->date(DateTimeHelper::fromSimpleDate('2024-01-15'))
        ->dateTime(DateTimeHelper::fromRfc3339DateTime('01/15/2024 09:00:00'))
        ->timeZone('America/New_York')
        ->build()
)
    ->id('abc123')
    ->summary('Team Weekly Standup')
    ->description('Weekly sync with the product team.')
    ->location('123 Main St, City')
    ->colorId('1')
    ->transparency(EventTransparency::OPAQUE)
    ->visibility(EventVisibility::DEFAULT_)
    ->sequence(0)
    ->attendeesOmitted(false)
    ->guestsCanInviteOthers(true)
    ->guestsCanModify(false)
    ->guestsCanSeeOtherGuests(true)
    ->build();

$conferenceDataVersion = ConferenceDataVersion::ENUM_0;

$maxAttendees = 1;

$sendUpdates = SendUpdates::NONE;

$supportsAttachments = false;

$eventsApi = $client->getEventsApi();
$apiResponse = $eventsApi->patchEvent(
    $calendarId,
    $eventId,
    $body,
    $conferenceDataVersion,
    $maxAttendees,
    $sendUpdates,
    $supportsAttachments
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'Event:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    if ($error instanceof ErrorResponseError1Exception) {
        echo 'ErrorResponseError1Exception:', $error;
    }
}
```

## Example Response *(as JSON)*

```json
{
  "kind": "calendar#event",
  "etag": "\"etag_value\"",
  "id": "abc123",
  "htmlLink": "https://example.com",
  "created": "2024-01-15T09:00:00Z",
  "updated": "2024-01-15T09:00:00Z",
  "summary": "Team Weekly Standup",
  "description": "Weekly sync with the product team.",
  "location": "123 Main St, City",
  "colorId": "1",
  "start": {
    "dateTime": "2024-01-15T09:00:00Z",
    "timeZone": "America/New_York"
  },
  "end": {
    "dateTime": "2024-01-15T10:00:00Z",
    "timeZone": "America/New_York"
  },
  "endTimeUnspecified": false,
  "recurringEventId": "abc123",
  "iCalUID": "unique-event-id@google.com",
  "sequence": 0,
  "attendeesOmitted": false,
  "hangoutLink": "https://example.com",
  "guestsCanInviteOthers": true,
  "guestsCanModify": false,
  "guestsCanSeeOtherGuests": true,
  "privateCopy": false,
  "locked": false
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request — invalid parameters or request body. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 401 | Authentication required or credentials are invalid. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 403 | Insufficient permissions for the requested resource. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 404 | The requested resource was not found. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |


# Delete Event

Deletes an event from the specified calendar.

```php
function deleteEvent(string $calendarId, string $eventId, ?string $sendUpdates = null): ApiResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `calendarId` | `string` | Template, Required | Calendar identifier. To retrieve calendar IDs call the calendarList.list method. Use the keyword "primary" to access the primary calendar of the currently logged-in user. |
| `eventId` | `string` | Template, Required | Event identifier. |
| `sendUpdates` | [`?string(SendUpdates)`](../../doc/models/send-updates.md) | Query, Optional | Guests who should receive notifications about the deletion of the event. |

## Requires scope

### oauth2

`https://www.googleapis.com/auth/calendar`, `https://www.googleapis.com/auth/calendar.events`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$calendarId = 'primary';

$eventId = 'abc123';

$sendUpdates = SendUpdates::NONE;

$eventsApi = $client->getEventsApi();
$apiResponse = $eventsApi->deleteEvent(
    $calendarId,
    $eventId,
    $sendUpdates
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'void:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    if ($error instanceof ErrorResponseError1Exception) {
        echo 'ErrorResponseError1Exception:', $error;
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request — invalid parameters or request body. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 401 | Authentication required or credentials are invalid. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 403 | Insufficient permissions for the requested resource. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 404 | The requested resource was not found. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 410 | Event has already been deleted. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |


# Watch Events

Sets up a push notification channel to watch for changes to events on the specified calendar. When events change, a POST notification is sent to the specified address.

```php
function watchEvents(string $calendarId, WatchRequest $body, ?array $eventTypes = null): ApiResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `calendarId` | `string` | Template, Required | Calendar identifier. To retrieve calendar IDs call the calendarList.list method. Use the keyword "primary" to access the primary calendar of the currently logged-in user. |
| `body` | [`WatchRequest`](../../doc/models/watch-request.md) | Body, Required | Request body for watch for event changes. |
| `eventTypes` | [`?(string(EventType)[])`](../../doc/models/event-type.md) | Query, Optional | Filters which event types to watch for changes. |

## Requires scope

### oauth2

`https://www.googleapis.com/auth/calendar`, `https://www.googleapis.com/auth/calendar.events`, `https://www.googleapis.com/auth/calendar.readonly`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`Channel`](../../doc/models/channel.md).

## Example Usage

```php
$calendarId = 'primary';

$body = WatchRequestBuilder::init(
    '01234567-89ab-cdef-0123-456789abcdef',
    ChannelType::WEB_HOOK,
    'https://example.com/calendar-webhook'
)
    ->token('my-verification-token')
    ->build();

$eventsApi = $client->getEventsApi();
$apiResponse = $eventsApi->watchEvents(
    $calendarId,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'Channel:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    if ($error instanceof ErrorResponseError1Exception) {
        echo 'ErrorResponseError1Exception:', $error;
    }
}
```

## Example Response *(as JSON)*

```json
{
  "kind": "api#channel",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "resourceId": "o3hgv1538sdjfh",
  "resourceUri": "https://www.googleapis.com/calendar/v3/calendars/primary/events",
  "token": "my-verification-token",
  "expiration": 1735689600000
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request — invalid parameters or request body. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 401 | Authentication required or credentials are invalid. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 403 | Insufficient permissions for the requested resource. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |
| 404 | The requested resource was not found. | [`ErrorResponseError1Exception`](../../doc/models/error-response-error-1-exception.md) |

