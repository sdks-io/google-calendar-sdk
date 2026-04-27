# Calendar List

Browse and manage the calendars on the user's calendar list.

```php
$calendarListApi = $client->getCalendarListApi();
```

## Class Name

`CalendarListApi`


# List Calendar List

Returns the calendars on the user's calendar list. Use the returned calendar IDs as the calendarId path parameter for event operations.

```php
function listCalendarList(
    ?int $maxResults = 100,
    ?string $minAccessRole = null,
    ?string $pageToken = null,
    ?bool $showDeleted = false,
    ?bool $showHidden = false,
    ?string $syncToken = null
): ApiResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `maxResults` | `?int` | Query, Optional | Maximum number of entries returned on one result page. Default is 100, maximum allowed is 250.<br><br>**Default**: `100`<br><br>**Constraints**: `>= 1`, `<= 250` |
| `minAccessRole` | [`?string(CalendarAccessRole)`](../../doc/models/calendar-access-role.md) | Query, Optional | The minimum access role for the user in the returned entries. |
| `pageToken` | `?string` | Query, Optional | Token specifying which result page to return. |
| `showDeleted` | `?bool` | Query, Optional | Whether to include deleted calendar list entries in the result. Default is false.<br><br>**Default**: `false` |
| `showHidden` | `?bool` | Query, Optional | Whether to show hidden entries. Default is false.<br><br>**Default**: `false` |
| `syncToken` | `?string` | Query, Optional | Token obtained from the nextSyncToken field returned on the last page of a previous list request. Makes the result contain only entries that have changed since then. |

## Requires scope

### oauth2

`https://www.googleapis.com/auth/calendar`, `https://www.googleapis.com/auth/calendar.readonly`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`CalendarListResponse`](../../doc/models/calendar-list-response.md).

## Example Usage

```php
$maxResults = 1;

$minAccessRole = CalendarAccessRole::READER;

$pageToken = 'CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA';

$showDeleted = false;

$showHidden = false;

$syncToken = 'CiAKGjJhbGVydHMvMTIzNDU2Nzg5MA';

$calendarListApi = $client->getCalendarListApi();
$apiResponse = $calendarListApi->listCalendarList(
    $maxResults,
    $minAccessRole,
    $pageToken,
    $showDeleted,
    $showHidden,
    $syncToken
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'CalendarListResponse:';
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
  "kind": "calendar#calendarList",
  "etag": "\"etag_value\"",
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

